## Minutes

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