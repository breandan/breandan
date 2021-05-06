## Minutes

# May 5, 2021

- I presented some examples of compositional generalization in natural and programming languages, and gave a demo of a tool for [regular language induction](https://en.wikipedia.org/wiki/Induction_of_regular_languages). This can be used to construct a regex matching a set of example strings. [Grammar induction](https://en.wikipedia.org/wiki/Grammar_induction) has been used for document classification and I believe is an important conceptual framework for modeling how developers [forage for information](https://web.eecs.utk.edu/~azh/blog/informationforaging.html).
- Jin raised some concerns about alignment with the downstream task. How do we assess whether our model is retrieving information that meets the information needs of the end user? This is related to how we define our context, and how we perform masking. We settled on a single-token prediction task like variable or method name prediction, which is similar to masked language modeling.
- I felt it was important that our model have the same "interface" for interacting with the search engine as a regular user would, i.e. our model should be able compress its contextual knowledge into a search query which retrieves relevant code snippets. Instead of computing an alignment with all documents, can we learn how to write a query to fetch the information, just like a human would?
- Xujie recommended looking into sketch-based program synthesis. He raised the point that prior work uses a graph or AST-based representation for source code. He also said that the project was large and suggested separating the project into smaller pieces, i.e. (1) source code recommendation part and (2) code-adaption. I agreed with Xujie that this was a good idea and would consider it.
- Jin asked me what I would like to achieve at the end of the summer. I would like to train a model that can learn to retrieve useful code snippets. I would also like to submit a paper to an [ML conference](https://jackietseng.github.io/conference_call_for_paper/conferences.html) this summer, possibly ICPR (July 10) or ICMLA (July 3). Finally, I would also like to update my [comprehensive exam](https://github.com/breandan/breandan/blob/master/paperwork/comp_exam/literature_review.pdf) to address the committee's [concerns](https://github.com/breandan/breandan/blob/master/paperwork/comp_exam/committee_letter.pdf).

# April 27, 2021

# April 13, 2021

Out of the papers we read this semester, I found Chen et al. (2020) one of the more difficult to follow. The motivation for the paper starts off straightforwardly: the authors want an architecture capable of generalizing to three specific settings (1) novel sequence length (2) novel combinations of previously commands ("template generalization" in the authors' nomenclature) and (3) novel contexts for commands seen exactly once in the training set (i.e. "primitive generalization").

To achieve this, they introduce a stack machine with a small instruction set (e.g. push/pop/reduce) which is learned by a neural controller to translate an input sequence, such as a natural language command (e.g. "walk left and run"), into a DSL (e.g. "LTURN WALK RUN"). In Figure 2, they provide an example of such an execution trace the neural controller might produce in practice:

![trace](https://user-images.githubusercontent.com/175716/115337065-5afdf780-a16e-11eb-933f-eb4e9be21c2e.png)

Between each step is an instruction produced by an operator predictor to control the stack machine, followed by a resulting state of the stack machine. In order to predict the operator, they predict an intermediate source and target "category" for each token in the source and target language. The authors also provide a separate figure for the architecture of the machine controller:

![diag](https://user-images.githubusercontent.com/175716/115337037-47eb2780-a16e-11eb-97a9-f02a55988afb.png)

The question arose of how latent category predictors were trained. Disha thought there must be some kind of intermediate supervision within each trace. I thought the only supervision was the loss over the final output sequence. This appears to be where the authors' definition of operational equivalence comes into play. The critical paragraph to understand here seems to be:

> ...after the trace search, we collect the non-degenerate operator traces, and compare among different samples within a training batch. If two samples share the same operator trace, we first assign their target sequences with the same target category for training.

Although unclear what exactly the authors mean by non-degeneracy here (perhaps it refers to when the predicted target sequence is correct), we turned our attention to the definition of operational equivalence, which became clearer after Disha corrected my initial interpretation:

![opeq](https://user-images.githubusercontent.com/175716/115338538-00b26600-a171-11eb-8344-2445295614c0.png)

Here, the authors are attempting to capture translational equivariance. Consider two correct translation pairs which share the same stack machine control sequence: although their source and target sequences might contain different tokens, if the operator traces for translating them are the same, then the source and target tokens within each trace should have the same categories. Disha then brought to my attention a more detailed algorithm from the Appendix, which their NeurIPS camera ready version did not contain.

![alg](https://user-images.githubusercontent.com/175716/115337319-c21bac00-a16e-11eb-99cc-91e3ca3f6495.png)

After spending a frustrating amount of time trying to decipher this algorithm and the surrounding text, we concluded there must be some kind of typo, since the outer index i does not appear in the inner loop. The terminology is difficult to follow, e.g. "lesson" which the authors never clearly define - appears to be analogous to one epoch of training, where a "batch" is a set of pairs of sentences in the source and target language.

Although Chen et al. (2020) has a number of redeeming qualities, including a nice definition of operational equivalence and a more precise definition of compositional generalization in its various forms, we agreed the exposition and algorithmic details leave much to be desired.

Next paper: [Language-Agnostic Representation Learning of Source Code from Structure and Context](https://arxiv.org/abs/2103.11318) by Zügner et al.?

# March 30, 2021

We discussed Didolkar et al.'s Neural Production Systems. From what I gathered, the main theme of our discussion was how to best employ relational inductive biases to realize a more refined combinatorial representation. Rather than considering all pairwise relations between input variables, can we construct a model which parses the input sequence into a graph "on the fly", whose edges represent correlated symbols, sub-symbols or input features?

The paper proposes to learn a relation between slots, conditions and actions. This follows in the footsteps of several recent architectures for key/value/query attention-based architectures. In the authors' view, slots represent discrete entities or arguments to a function (here, they draw an analogy to variable binding in programming languages). They also draw connections to graph neural networks and cognitive science. Taking inspiration from Lovett & Anderson, they emphasize four important characteristics of production systems:

* **Modularity** - Rules represent a discrete "unit" of knowledge that can be reused independently and interchangeably.
* **Abstraction** - Rules specify attributes of entities, rather than entities themselves. They argue this feature allows them to more robustly generalize to new entities.
* **Sparsity** - To effectively make use of resource-constrained hardware, the model must selectively attend to input variables. By imposing a sparsity constraint, they can leverage available resources to greater effect (e.g. longer range dependencies on more complex data).
* **Causality** - Relations are directed and asymmetric, where each rule represents a condition under which an action should be applied, and the action represents updating an internal state based on learned conditions.

Disha shared two concerns regarding the proposed attention mechanism, and would have liked to have seen a comparison between hard and soft attention. She expressed some confusion about the choice of sequential rule application in spite of its admittedly weak performance and suggested that adding a multi-head attention component could have provided a beneficial effect.

I asked Disha what additional experiments she would have liked to see. She responded that visualizing and interpreting the activations on various tasks would be beneficial. Does addition and multiplication activate certain slots? She also remarked that comparing with other sparse architectures, e.g. Sparse graph attention networks would have been helpful to see.

David remarked that the model's choices aligned with the intuition of some researchers for how the brain works, although he cautioned against relying too heavily on intuition, and advocated for the benefits of writing down code. He also argued for a more explicitly subsymbolic approach. We agreed that intuition can sometimes be misleading when used to justify our own reasoning.

I asked David whether he saw a way to incorporate subsymbols into the authors' scheme of slots of keys, and he proposed a form of energy-based modeling to map subsymbolic representations with symbols, with contrastive divergence for training. We exchanged some thoughts about the computational benefits of sparsity, which I know various software libraries are using.

The high-level theme is that instead of generating a scalar or vector value for each input, these networks attempt to generate a set of relations between slots and rules. In effect, they are learning a mapping between unstructured data and a graph whose edges represent correlated input variables. These graphs are generated directly by propagating the input state forward once, instead of via backpropagation and extraction. The idea appears to be a very active area of research in sequence prediction, programming, and other symbolic reasoning domains.

## March 16, 2021

[Emergent Symbols Through Binding in External Memory](https://arxiv.org/pdf/2012.14601.pdf)

Limitations of the paper:

We first discussed some limitations of the paper.

    -David suggested that pre-segmented clean images was too naive, and
    would liked to have seen a model which learned the task from a 
    single image composed of multiple symbols.
    -Breandan did not understand why embedding an image of a unicode 
    character was necessary to begin with, if they are just using the 
    clean segmented image.
    -Disha made the observation that according to the authors, their primary
    contribution was introducing binding and indirection as two separate
    components, but then they later suggest it limits the relations 
    that can be learned.

Model Architecture

We had some confusion about the architecture.

    -Breandan did not understand the architecture and asked for clarification.
    -David said the key to understanding the architecture was a single
    sentence, "[we] then pass [the image] embeddings to a sequential model 
    component f_s..."
    - Disha asked why the if/else block was necessary in Algorithm 1 and
    speculated that it corresponded to the author's implementation of the
    temporal context normalization (TCN)
    - Someone asked whether the archiecture was trained end-to-end.
    I later found this sentence on page 4, P2: "All components are trained 
    end-to-end, including the encoder."

Experiment design and results

We then turned our attention to the task.

    - David wondered whether pattern completion was a reasonable task
    and what a more realistic task might be? 
    - Disha suggested maybe using physically-based reasoning, i.e. blocks 
    and spheres and their relations.
    - There was some discussion about whether the task could be solved
    in object space or latent space then decoded to a prediction.
    - Breandan asked what feature allows the ESBN to converge so quickly?
    - Disha and David explained that TCN and the model architecture
    effectively disentangling relations from objects. This forces an 
    inductive bias, where transformers must learn relations from scratch
    the ESBN explicitly discriminates between items it has seen before.

Fuzzy ideas

Finally, we shared some philosophical observations about language.

    - David said that symbol construction from pixels was kind of like a
    monad, with compositional properties.
    - Disha asked whether we thought the author's view of emergent s ymbols  was reasonable?
    - David and Disha shared their thoughts on reuse in language.  
    - David contrasted "Here is a horse" (instance of category, in English) and "Here is horse" (category, in Chinese) and suggested some connection to key-value storage format.
    - Breandan speculated that externalizing internal thoughts functioned
   as some kind of loop closure.

Next paper: [Neural production systems](https://arxiv.org/pdf/2103.01937.pdf)?

## March 2nd, 2021

[Learning Compositional Rules via Neural Program Synthesis](https://arxiv.org/pdf/2003.05562.pdf)

- **Only superficial resemblance with Meta-learning**: Disha's initial contention was that the paper's resemblance to metalearning was overstated.
  - The proposed training process had no outer loop or meta train/test split
  - Simple encoder-decoder architecture with few metalearning adaptations.
  - Authors used fundamentally the same task at training and test time.
  - David remarked the results could be partially explained by the MLE objective.
- **Sampling procedure / Fairness of evaluation**: There was a considerable amount of skepticism around the validity of the search procedure.
  - David did some arithmetic and speculated the search procedure was nearly exhaustive for the toy grammar shown. If so, why bother learning at all?
  - Disha was suspicious of the sharp contrast between search-based and search-free synthesis cross-language generalization, possibly indicative of overfitting.
  - Breandan questioned the feasibility of performing an apples-to-apples comparison with DeepCoder and other methods due to the unique evaluation strategy.
  - Breandan asked why didn't the authors use structured prediction or hierarchical sampling techniques? David replied that it might be too inflexible to meet developers' evolving needs.
  - David suggested using attention / contextual relevance as a mechanism for identifying types. Maybe this could help to reduce the search space by pruning similar branches.
- **Learnability of specification/grammar relation**: There was some discussion about whether the model was actually generalizing and what the model was learning specifically.
  - David suggested the model was learning what to discard and said the problem might be unlearnable due to the distributional shift between support and query set.
  - Breandan suggested partial fulfillment of specifications with a gradient-based sampling procedure, possibly using a form of beam search or MCTS.
  - Disha made some suggestions including using Gumbel softmax to support differentiable sampling.

In summary, Disha had three primary concerns with the proposed method:

1. Potentially overfitting. Timeout-based termination was impractical.
2. Not truly meta-learning (no outer loop, train/test tasks were not different).
3. Unconvincing generalization. What specific component allows for generalization?

## February 22nd, 2021

- Why is this an important problem?
- Usefulness of the evidence between the context
- Look at the prior literature
- Where does the data come from?
- Send update on Tuesday
- What kind of data do you want to gather?
- Assign the new task, maybe code completion
- Need to compare with current state of art
- Comparison with SOTA, select a task

## February 16th, 2021

[Write, Execute, Assess: Program Synthesis with a REPL](https://arxiv.org/pdf/1906.04604.pdf)

- Reasonability of assumptions
  - David raised some concerns over the (pp, spec) pair and how it might be unreasonable to be handed a fully-formed specification for each rollout.
  - Disha raised some concerns about the 0-1 loss and how it would be helpful to have a soft loss that was able to reward partial specification matching.
  - Breandan was concerned the specification and program synthesizer does not attempt to match human data and might not align with human preferences.
  - We agreed the paper was a cut-and-dry application of RL to program synthesis. Although somewhat simplistic, it was a good start.
- Necessity of stochasticity
  - Disha raised a question regarding the necessity and advantages of stochasticity for learning. What benefit does stochasticity confer for program synthesis?
  - David mentioned the importance of stochasticity in crossing the sim-to-real gap and learning a controller stable to noise in the environment.
  - Breandan described the distinction between aleatoric and epistemic uncertainty and how black box deterministic functions look stochastic when viewed externally.
  - We agreed that Ellis et al. used stochasticity primarily in the specification sampling procedure.
- Architectural improvements
  - Breandan proposed giving the transition model freedom to generate nonlocal or context-sensitive edits to the state, possibly increasing expressivity.
  - David asked whether these edits would break context-freedom of the grammar and proposed learning from context using an LSTM architecture.
  - Disha asked what alternatives to REINFORCE of policy gradient methods might be useful to consider in the context of program synthesis.
Future directions
-   Disha wants to explore using execution-guided synthesis with PO/MDPs and incorporating line-based/sequential synthesis in the style of PCCoder and DeepCoder
  - David wants to build symbolic representations from subsymbolic parts, exploring composition and reuse in natural language, possibly some alignment with programming.
  - Breandan wants to use probabilistic programming to write programs to generate functions in a language which are closed over itself and incorporate human preferences.
  - We agreed there was some alignment between our interests.
Meeting logistics
  - We agreed to meet every other week to discuss papers this Spring.
  - We can rotate reading suggestions depending on the week
  - Maybe Disha, then David, then Breandan can drive the discussion?

## December 9th, 2020

- Clarify research goals / evidence for ideas rules are learnable
- Can we learn the ontology from code?
- Deriving the rules from code?
- Which domain are we targeting?
- Well-defined ontologies?

## December 2nd, 2020

- Book a meeting with Xujie before he gets too busy
- Look into Miryun Kim's work on probabilistic code search
- Send formal invitations to supervisory committee
- Finalize countersigned letter of understanding with Jin
- Jan Vitek / Fitzcarraldo discussion with KAST on Friday
- Make a decision about MILA TAship this Spring

## November 12th, 2020

- Breandan: Code search / recommendation (SO, GH)
  - Kian: Look at neighborhood similarity metrics
- Fuyuan: Auto-translating eDSLs (e.g. PyTorch-TF)
- Kian: Predicting GitHub activity (e.g. commits)

## October 28th, 2020

- Connecting with prior work
- How to relate with rewriting?
- Plan experimental design / small experiment demonstrating potential
- Acceptance testing and user story
- Problem scenarios we can address
- Scope for matching procedure
- Code-code / NL-code. Choose!

## October 21, 2020

- Bidirectional model card editing / Sixian
- Duplicate detection is called many things in many communities
  - Common subexpression detection/elimination
  - Code clone detection
  - Semantic similarity detection
  - Bisimulation...
- Code clone/duplicate detection is maybe not the right direction
- We want to find code that was independently written, but same semantics
- Look into example-based programming / programming by example
- Feasibility of using rewriting techniques for end user applications
- Rewriting as either a query expansion or data augmentation technique?
- System-level design (motivate the design using an end-user application)
- How do you identify the rewrite rules / semantics?
- Compiler literature forces strict equivalence between rewrites
    - Possible to relax rewrites to include near matches
    - Might want to discard certain specifics, e.g. literal values
- How to apply the transformations to the model?
    - Chicken-and-egg problem of how to discover rewrites
    - Which rewrites you can perform affects expressivity of grammar
- Levels of understanding / granularity of rewriting
    - Method level
    - Cell level
    - Expression level...
- Application motives the design choices we make
- Co-design of the application and the tool
- Relaxing the rewrite semantics to maybe discard information
- Confirm the timing of the syllabus and exam proposal with the department
- Gap between primitive methods and end user scope
- How to break up the roadmap from research to adoption?
- Who is the appropriate audience?
- How to tailor the deliverables to target the audience?
    - i.e. how to "sell" to SE/PL/ML/HCI community
- Bridging examples from these communities in literature review
    - Should reflect the research you aspire to publish
- What is the long term goal here?
    - Living thesis, turn research into a real project
    - Build a tool to suggest similar code snippets in realtime?

- COMP 598: SE for Intelligent Systems
    - Grading M1 submissions
    - Check the logs for errors?
    - Does the service run / stability / QoS
    - Recitation for M2 next Wednesday
        - CI/CD, testing, testing methods, coverage
    - Check the slides from testing lecture
    - Do we need to add/provide any additional features on server?

## September 30, 2020

- Discuss COMP 598 lab / recitation
- Standups resuming next Mon/Wed

## September 24, 2020

- Rework intro to emphasize
    - Contribution w.r.t. 2d-supervision (videos)
    - Compare with (less) interpretable neural/implicit parameterization
- Describe generalization to real videos from motion capture
- Filtering out halos

## September 21, 2020

- Research summary and updates w/XJ
- OK for progress committee

## September 4th, 2020

- Reductions

## August 31, 2020

- Working in Montreal (quarantine for 14 days)
- Three classes, required to complete one more
- Preparing for comprehensive examination at the end of the year
- Registered for Foundations of Computational Linguistics / LING 645
- Failed one class, another failure will result in expulsion from Ph.D. program
- Will send invitation to progress committee with proposal abstract
- Complete annual progress report summarizing research progress
- Registered for SOCS TA training for COMP 598 on Sept. 9th
- Preparing infrastructure for COMP 598, meeting on Monday Sept. 7 at 2:30pm
- Will attend the first few classes and help as needed
- Opportunity to give guest lecture with advance notice (e.g. infra/testing)
- Need to respect others time and honor our commitments (e.g. weekly updates)
- Failed to show up for the CMU meeting on Aug. 25th, 2020
- CMU meetings rescheduled to Fridays, tread lightly
- Lab meeting rescheduled to Wednesdays

## August 14, 2020

- Reasoning about program changes and semantic representations
- Incremental rebuilding and fast/reactive notebooks
- Developing the research question, taking steps towards concrete topic
  - Focus on the process, need to work on these skills
- Connecting AutoML and SE for IoT
- Friday meetings, continue to meet with Christian
- Comprehensive exam prep, BBQ and classes

## July, 18, 2020

- Focus on task evaluation
- What task are we going to use?

## July 16, 2020

- Automated model card generation

## July 14, 2020

- Two more weeks, start writing up results
- Shape, type, mean, range, variance documentation
- Brainstorming what tasks can these documentation tools be good for?

## July 7, 2020

- Notebook webpage, delta debugging / Jerry
- Generating documentation (e.g. types, distributions) / Chenyang
- Daikon and invariant detection (Michael Earnst) / Christian
- DVC and workflow, invertible computation / Mark

## June 25, 2020

- Semantic code search, subgraph isomorphism, Z3 / Breandan
- Code statistics

## June 24, 2020

- Categorizing sklearn API methods / Grace
- Stages: collection cleaning labeling training evaluation deployment / Cindy
- Color coding of cells and execution order of cells
- Sampling strategies, does GitHub always sort by popularity? / Breandan
- Jupyter NB extension / [Dataflow Kernel](https://github.com/dataflownb/dfkernel) / Jerry

## June 23, 2020

- One-on-one as needed
- Missing progress on survey
- PEQ paperwork and McGill registrar update
- Attended three talks at AKBC conference
  - Luke Zettlemoyer - Denoising seq2seq pretraining / MARGE
  - Ndapa Nakashole - natual language to charts: [ChartDialog](https://github.com/sythello/ChartDialog)
  - Emma Strubel - SOTA in NLP, interesting digression on model efficiency and benchmarks
    - Wall clock time is too variable
    - FLOPs can be meaningless on different hardware
    - Maybe kWh consumed?

## June 19, 2020

- [codenames](https://github.com/jbowens/codenames) with Kast

## PLDI 2020

- [MAPL workshop](https://pldi20.sigplan.org/home/mapl-2020) ([on YouTube](https://www.youtube.com/watch?v=rwBbYhOAnPo))
  - Hoppity: Learning Graph Transformations to Detect and Fix Bugs in Programs
  - LambdaNet: Probabilistic Type Inference using Graph Neural Networks
  - Semi-static Type, Shape and Symbolic Shape Inference for Dynamic Computation Graphs
  - Program Optimization for Machine Learning
  - Learned Garbage Collection
  - Neurosymbolic Reasoning and the Third Wave of Program Synthesis
- [PMLW](https://www.youtube.com/watch?v=MqUcMIlKk8Y)
  - Eran Yahav - Program representation intro / paths / ASTs / Code2Vec
  - Ali Donaldson - How to compensate for lack of novelty in PL
- [Ask Me Anything](https://www.youtube.com/watch?v=wESqGFzek-Y)
  - Margaret Martonosi - National Science Foundation
  - Michelle Strout - Embedded Domain Specific Languages!
  - Alex Aiken - Machine learning / PL
  - Kathleen Fischer - Government, industry and academia + DSLs
  - Chris Lattner - Compiler stuff
  - Guy L. Steele - Fortress and parallelism, soft skills, anecdotes

## June 16, 2020

- Provenance, classifying notebook structure and user process
- Static analysis, clarifying intended use case and audience
- Dead code, program dependence, use-def/def-use relations
- Identifying "stale" notebook cells and gathering up code

## June 11, 2020

- Integration with existing tools (e.g. Docker) / Breandan
- What is each version doing? (add cell, some semantic change) / Fuyuan
    - [A gallery of interesting Jupyter Notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks)

## June 10, 2020

- Proposed three tools
  - https://github.com/coetaur0/staticfg
  - https://github.com/ChrisCummins/ProGraML
  - https://github.com/JetBrains-Research/astminer
- Using [nbgather](https://github.com/Microsoft/gather)

## June 9, 2020

### Notebooks meeting

- Why doesn't the noworkflow tracer output dot graph?

### Advisor meeting

- Systematic literature review
  - Queries
  - Snowball sampling
  - Data analysis (raw data)
- Create an Overleaf project about comp exam
  - Write about rough research questions
  - Define each term and cite
  - Focus and granularity and length
  - Ask Mathieu about required amount of literature
      - source code analysis
      - 6 papers related to field
      - program comprehension
- "program synthesis and applications for programming tools to support search"?
- notebooks, interpretability, work on the initial list
- Send progress committee draft invitation letter

## June 8, 2020

- [Hypermodern Python](https://cjolowicz.github.io/posts/hypermodern-python-01-setup/)
      - [typing](https://cjolowicz.github.io/posts/hypermodern-python-04-typing/) - mypy, pyre, pyright, pytype
  - [CI/CD](https://cjolowicz.github.io/posts/hypermodern-python-06-ci-cd/) - poetry
  - [documentation](https://cjolowicz.github.io/posts/hypermodern-python-05-documentation/) - sphinx, rst

## June 5, 2020

### Advisor meeting

- Adgenda: Comprehensive exam, progress committee, notebook deliverables

## June 4, 2020

### Physics meeting

- Visual MPC experiments need to be higher resolution / Krishna + Vikram
- LaTeX compression to fit in 8 pages / Sanja
- Last 3.5-4 pages should be results / Krishna
- Describe why the results are important / Derek
- Add pendula experiments to supplementary material (due Jun. 11, 1pm) / Breandan

### KAST meeting

- GraphViz + NoWorkflow now works / Grace
- [DAGsHub](https://dagshub.com/) / Fuyuan
- Source preserving IR transformations / Breandan
- Put together concrete goals document / Jin

## June 2, 2020

- Analysis of notebooks: adapting type inference and other tools / Jerry
- Empirical studies: best practices and notebook analysis? / Isabel

### TODOs

- Obtain UdeM diploma from registrar & update McGill about M.Sc. graduation
- Submit advisor co-signed MOU from Ann's email (July 6th)
- Follow up on doctoral progress committee formation
- Submit qualifying exam syllabus to department
- Update Jin on planned contributions to notebook project (Fri)
- Submit final IFT6759 TA invoice to Joumana

## May 29, 2020

- [python-program-analysis](https://github.com/microsoft/python-program-analysis) => [nbgather](https://github.com/Microsoft/gather) / Jerry
- [noworkflow](https://github.com/gems-uff/noworkflow) / Grace
- Flow sensitive and context sensitive analysis, test cases:

```python
x[1] = b
x[2] = c
print(x[1])

x.a=b
x.b=c
print(x.a)

def first(a,b): return a
x = first(a, b)
print(x)

x = first(a, b)
y = first(c, d)
print(x)

if (random() < 0.00001) x = a else x = b
print(x)
```

- Meeting again Tuesday, 11:15am

## May 28, 2020

- Triangles vs. tetrahedra
- Reducing the number of triangles
- IoU: intersection over union / Sanja
- Amortized inference using neural nets
- How does rendering gradients help?
- Introduction needs more attention
- Finite difference pybullet?

## May 27, 2020

### ISR Meeting / Christian + Jin

- Ready made tool for DVC hyperparameters + versioning /  Fuyuan
- Guessing libraries, modules and reproducibility [Burrito](https://dash.harvard.edu/bitstream/handle/1/9938866/Guo_BURRITOWrapping.pdf)? / Isabel
- Generating model cards for notebooks / Grace
- Pyre and type checking, dead code, constant propagation / Cindy
- Out of order notebooks. Transform to SSA form = CPS? / Jerry
- Fingerprinting and common refactoring patterns / Breandan
  - Incremental computation, cell segmentation, data flow, info flow
  - Splicing compatible snippets and slicing techniques
  - Identifying clean and dirty pairs: what are people doing?
  - Possible applications: clone detection / similarity search
  - Look into literature: [Katie Stolee](https://scholar.google.ca/citations?user=dmcgQDQAAAAJ&hl=en&oi=sra), [Crista Lopes](https://scholar.google.com/citations?user=FaY_RgsAAAAJ&hl=en)
  - Connect with Mark about refactoring
- Meeting Tuesday 12-1pm (Isabel, Helen) / Friday 3-4pm (group temp)

### Qualifying exam planning / Jin

- Contextually relevant information retrieval
- Explainability and interpretability
- Incorporate prior experience into thesis proposal
- What do we want to understand about the user? Who is the audience?
- Methods oriented vs. solution oriented research
- Put together concrete plan with specific contributions
- Select two papers from HCI/SE to anchor discussion
- Mini-proposal / skeleton for qualifying exam

## May 26, 2020

- Meeting tomorrow with ISR folks
- Program slicing, rewriting & refactoring / Breandan
    - Skeleton and fit refactoring into the thesis
- [Jupyter notebook extensions](https://jupyterlab.readthedocs.io/en/stable/developer/extension_tutorial.html#extension-tutorial) / Grace
- [MLV-Tools](https://github.com/peopledoc/mlvtools-tutorial) / Fuyuan
- [Quality and Reproducibility of Jupyter Notebooks](http://www2.ic.uff.br/~leomurta/papers/pimentel2019a.pdf) / Fluminense

## May 21, 2020

- Mass estimation for deformable objects
- RMSE and physical parameters in experiments
- Where does the rendering component come in?
- Identifying ambiguous graphics/physics scenarios / Florian
  - Can adding differentiable physics / rendering resolve?
- Rigid body versus deformable physics / Derek
- Unsupervised parameter estimation from video
- Go / no go for deadline next week
- Pendula sensitive to some parameters (rod length)
- Runge-Kutta and step size

## May 19, 2020

- DVC and version control for data pipelines / Fuyuan
- Program slicing and notebook analysis / Grace
- Notebook debugging and visualization / Breandan
- Look into static vs. dynamic slicing
- Put together weekly report for next meeting
  - Summary, Progress, Challenges / Questions, Plans

## May 18, 2020

- Angluin's L* algorithm for language learning
- Context representation and document graph structure
- Reprioritizing publication goals
- Missed three deadlines: FSE, ASE, NeurIPS
- Research lacks experimental validation
- Unclear progress towards thesis goals
- Time commitment to KAST and other activities
- Need to put together a plan of remediation
- Notebooks meeting Tue May 19th 2-3pm
- Weekly meetings moved to Tuesdays 3-4pm