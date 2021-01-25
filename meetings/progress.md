## Todo

- Research
  - [ ] Design experiment to test graph matching
  - [ ] Implement random walk rewriter on real data
  - [ ] Inductive biases and inductive definitions
  - [ ] Dependent type theory talk
- Other bets
  - [ ] Describe Kotlin∇ invocation semantics
  - [ ] Describe higher order/rank derivatives
  - [ ] Describe automatic vs. symbolic difference
  - [ ] Describe code generation / macro approach
  - [ ] Binary matrix API and other semirings
  - [ ] Implement term rewriting in Kaliningraph
  - [ ] Implement doubly-linked graph API
  - [ ] Compile arithmetic circuit to a matrix
  - [ ] [ISSAC](http://issac-conference.org/2021/) with Alex

## January 25, 2020

- Last week
  - [Lit review](https://raw.githubusercontent.com/breandan/breandan/master/paperwork/literature_review.pdf)
  - [Markov chain code synthesis](https://github.com/breandan/markovian/blob/master/src/main/kotlin/edu/mcgill/markovian/mcmc/MarkovChain.kt)
  - [Computer Calculus RG](https://compcalc.github.io/)
  - POPL / LAFI
- This week
  - [Comprehensive exam](https://raw.githubusercontent.com/breandan/breandan/master/presentations/comprehensive_exam.pdf)
- Next week
  - AD in PyTorch lecture
- Reading
  - [Relational inductive biases](https://arxiv.org/pdf/1806.01261.pdf)
  - [Path problems in networks](https://www.morganclaypool.com/doi/abs/10.2200/S00245ED1V01Y201001CNT003)

## Jan 18th, 2020

- Progress
  - Define procedural knowledge as a directed knowledge graph
  - Revisit hypergraph grammars and message passing algorithms
  - Set/Tree/Graph kernels and define objective function
  - Incorporate Xujie and Fuyuan's feedback. Thank you!
- Challenges / Questions
  - Writing
  - Timeliness
  - Identifying related literature
- Next week
  - Prepare slides and talk

## December 16th, 2020

- Last week
  - Probabilistic knowledge graphs
  - Ontological graph representations
  - NeurIPS / [CAP](https://capworkshop.github.io/) / DiffCV workshops
- This week
  - Prepared for PGM poster session
  - Writing final report for IFT-6269
  - Finish grading COMP 598 final projects
  - ICML workshop organization planning
  - Planning for speech recognition course
- Reading
  - [Every Model Learned by Gradient Descent Is Approximately a Kernel Machine](https://arxiv.org/pdf/2012.00152.pdf)
  - [Implementing the Giry Monad](https://jtobin.io/giry-monad-implementation)
  - [Factor Graph Grammars](https://proceedings.neurips.cc/paper/2020/file/49ca03822497d26a3943d5084ed59130-Paper.pdf)
  - [miniKanren as a Tool for Symbolic Computation in Python](https://arxiv.org/pdf/2005.11644.pdf)
  - [What You Always Wanted to Know About Datalog](https://personal.utdallas.edu/~gupta/courses/acl/papers/datalog-paper.pdf)

## December 9th, 2020

- Last meeting
  - Probabilistic reasoning and inference
  - Presented prototype DSL for ProbProg
  - Toy implementation of GMM/SPN
- This week
  - Ontologies and graph representations
  - Big code as a procedural knowledge base
  - Translating expert knowledge to code
  - Knowledge-based code generation
- Reading
  - [Relationships between probability distributions](https://en.wikipedia.org/wiki/Relationships_among_probability_distributions)
  - [ProbOnto 2.5: Ontology and Knowledge Base of Probability Distributions](https://sites.google.com/site/probonto/home)
  - [Empirical Metamaths](https://writings.stephenwolfram.com/2020/09/the-empirical-metamathematics-of-euclid-and-beyond/)
  - [Semantic Code Search via Equational Reasoning](http://www.jameskoppel.com/files/papers/yogo-preprint.pdf)
  - [Active ILP for Code Search](http://starai.cs.ucla.edu/papers/SivaramanICSE19.pdf)

## December 2nd, 2020

- Finished up grading COMP 598 M2
- Submitted exam proposal / SOCS paperwork
- Submitted PGM progress report
  - from BNs to PCs
  - PCs and PCFGs
- Reasoning about uncertainty experiments
- Software release engineering lecture
- Feedback to Kian
- Reading
  - [Propagator networks](https://dspace.mit.edu/bitstream/handle/1721.1/54635/603543210-MIT.pdf)
  - [Graph Kernels](https://arxiv.org/pdf/2011.03854.pdf)
  - [Semantic Code Search via Equational Reasoning](http://www.jameskoppel.com/files/papers/yogo-preprint.pdf)

## November 18, 2020

- Last meeting
    - Lit review
    - ICML reviews
    - ICLR workshop submission
    - Feedback for COMP 598 / M1
- This week
    - Writing PGM final project
    - Writing comprehensive exam
    - Writing code / graph prop
    - Link stack traces to GitHub
    - Link IDE context to StackOverflow
- Challenges
    - Need to be more focused
- Reading
    - [Probabilistic Circuits](http://starai.cs.ucla.edu/papers/ProbCirc20.pdf), Choi et al. (2020)
    - [Lancer: Your Code Tell Me What You Need](http://www.cs.sjtu.edu.cn/~zhonghao/paper/Lancer.pdf), Zhou et al. (2019) [[source code](https://github.com/sfzhou5678/Lancer)]
    - [TraceSim: A Method for Calculating Stack Trace Similarity](https://arxiv.org/pdf/2009.12590.pdf), Vasiliev et al. (2020)
    - [Exploiting Code Knowledge Graph for Bug Localization via Bi-directional Attention](https://doi.org/10.1145/3387904.3389281), Zhang et al. (2020)
    - ...

## November 11, 2020

- Last meeting
  - Described experimental setup: SO queries
  - Treating embedded code snippets as IDE text
  - Can we recover the e.g. "garbled" text somehow?
- This meeting
  - Approximate string matching / sequence alignment
  - Query string (e.g. whole stacktrace + code)
  - What SO questions match the query most closely?
  - Possible to model sequence as a HMM production
  - Similarities to pattern matching on genetic data
  - Possible to leverage byte pair encoding (BPE)
- Challenges
  - Need an online algorithm that is fast + efficient
  - Compare and contrast with vector space encoding
  - Depending on complexity, may not be tractable to search entire database
- Reading:
  - [Learning to Fix Programs from Error Messages](https://ai.stanford.edu/blog/DrRepair/)
  - [Approximate Online Pattern Matching in Sub-linear Time](https://arxiv.org/pdf/1810.03551.pdf), Chakraborty et al. (2018)
  - [Improved online algorithms for jumbled matching](https://doi.org/10.1016/j.dam.2018.05.028), Ghuman et al. (2018)
  - [Parallelizing Exact and Approximate String Matching via Inclusive Scan on a GPU](http://www-hagi.ist.osaka-u.ac.jp/research/papers/201707_mitani_ieeetpds.pdf), Mitani et al. (2017)
  - [A Novel Algorithm for Online Inexact String Matching and its FPGA Implementation](https://doi.org/10.1007/s12559-019-09646-y), Cinti et al. (2019)
  - [Context-Free Path Querying by Matrix Multiplication](https://doi.org/10.1145/3210259.3210264), Azimov and Grigorev (2018)

## November 4, 2020

- Last meeting
  - Graph matching in SLAM/computer vision
  - Compressed sensing in signal processing
  - Representations which capture invariance
  - Put together a concrete experiment
- Progress
  - Program repair / programming by example
  - Fixing compiler errors using SO as a KB?
  - Extract context from sources and stacktrace
- Reading
  - [Hoppity: Learning Graph Transformations to Detect and Fix Bugs in Programs](https://openreview.net/pdf?id=SJeqs6EFvB), Dinella et al. (2020)
  - [Learning Lenient Parsing & Typing via Indirect Supervision](https://arxiv.org/pdf/1910.05879.pdf), Ahmed et al. (2020)
  - [Can We Use Stack Overflow as a Source of Explainable Bug-fix Data?](https://arxiv.org/pdf/2004.08378.pdf), Tang and Nadi (2020)
  - [Optimising the Fit of Stack Overflow Code Snippets into Existing Code](https://arxiv.org/pdf/2004.07663.pdf), Reid et al. (2020)
  - [From Query to Usable Code: An Analysis of StackOverflow Code Snippets](https://dl.acm.org/doi/pdf/10.1145/2901739.2901767), Yang et al. (2016)

## October 28, 2020

- Last meeting
  - Try to broaden scope to include programming by example
  - Thinking about the concrete application will help keep us on track
  - How to adapt the deliverables to fit the audience
- Progress
  - Prepared recitation #2, [Concepts in Statistical and Software Testing](https://github.com/breandan/kotlingrad/blob/master/latex/testing/testing.pdf)
  - Thought about how to model user edits on a codebase as a Markov chain
  - Probabilities of editing a specific file based on the edge connections between entity references
  - Could use this to recommend a list of files missed in a commit (e.g. unlinked string references)
- Reading
  - [Subgraphs in the trace of a random walk](https://arxiv.org/abs/1605.04585)
  - [Factor graph grammars](https://arxiv.org/abs/2010.12048)
  - [Aleatoric and Epistemic Uncertainty in Machine Learning](https://arxiv.org/abs/1910.09457)
- Plan for next week
  - Finish up the exam syllabus and send draft for review

## October 7, 2020

- **Last meeting**
  - Equivalence in the context of computational notebooks
- **Progress**
  - Started evaluating [SMT solver](https://github.com/breandan/kaliningraph/blob/master/src/main/kotlin/edu/mcgill/kaliningraph/smt/TestSMT.kt) for graph canonicalization
  - Developed [research questions](https://github.com/breandan/kaliningraph#research-questions) for Kaliningraph
  - Read about theories for [graph rewriting in Grez](http://www.ti.inf.uni-due.de/fileadmin/public/tools/grez/grez-manual.pdf#chapter.5)
- **Challenges and questions**
  - In general, checking rewrites for termination is [undecidable](https://www.researchgate.net/profile/Detlef_Plump/publication/37923776_Termination_of_Graph_Rewriting_is_Undecidable/links/0046351a879627f6e2000000.pdf)
  - Need to identify a decidable fragment of language and rewrites
- **Plan for next week**
  - Visualize graph/snippet rewrite system in a notebook setting
  - Define/implement reduction semantics for canonicalization
  - Finish writing DSL for graph reduction definitions

## September 30, 2020

- **Last meeting**
  -  Discussed architecture and research plans
  -  Develop project in the context of PGM class
- **Progress**
  -  Formalized definition of equivalence
- **Challenges and questions**
  -  Finding a killer application
- **Plan for next week**
  -  Submit project proposal for feedback
  -  Put together outline for comprehensive exam

## September 23, 2020

- **Last meeting**
  - Chat with Xujie. Ok for the progress committee
  - Exact equality is hard to define, maybe relax constraints
- **Progress**
  - Drafted an [architectural diagram](https://drive.google.com/file/d/1xfiI4fuCYdbXjSmm70fXxLxH3rGspQCd/view?usp=sharing) to visualize dataflow
  - Worked on the [probabilistic sampler](https://github.com/breandan/katholic)
- **Challenges and questions**
  - Identifying what (e.g. end-user) applications we want to support
- **Plan for next week**
  - Work on IFT 6269 homework #2
  - Invite progress committee members
  - Cataloging papers for the comprehensive exam
- **Reading**
  - [Learning to Solve SMT Formulas (2018)](http://papers.nips.cc/paper/8233-learning-to-solve-smt-formulas.pdf)
  - [Equivalence of Dataflow Graphs via Rewrite Rules: Using a Graph-to-Sequence Neural Model (2020)](https://arxiv.org/pdf/2002.06799.pdf)
  - [Extensibility for the Masses: Practical Extensibility with Object Algebras (2012)](http://www.cs.utexas.edu/~wcook/Drafts/2012/ecoop2012.pdf)

## September 16, 2020

- **Last meeting**
  - Structured encoding/decoding
  - Are notebooks still a good fit?
  - Reaching out for feedback
- **Progress**
  - Thought about evaluation
  - Functional testing of code snippets
  - Setup infra for COMP 598
  - Looked into SMT solvers and MiniKanren
- **Challenges**
  - Formally defining equality and semantic similarity
  - Overlap with prior work (see below)
- **Next Week**
  - Work on IFT 6269 homework
  - Progress committee formation
- **Reading**
  - MISIM: An End-to-End Neural Code Similarity System (2020)
  - funcGNN: A Graph Neural Network Approach to Program Similarity (2020)
  - Learning Semantic Program Embeddings with Graph Interval Neural Network (2020)
  - Detecting Code Clones with Graph Neural Network and Flow-Augmented Abstract Syntax Tree (2020)
  - Algebraic Graphs with Class (Functional Pearl) (2017)

## September 9, 2020

- **Last meeting**
  - Summarize progress on [approximating source code semantics](https://docs.google.com/presentation/d/1KTUUwj7CsUhMANoNTzyDWaV02JLuBXqI9xFKNjAamM4/edit?usp=sharing)
- **Progress**
  - Implement [distribution matching](https://github.com/breandan/katholic/blob/master/src/main/kotlin/DSL.kt) for simple algebraic expressions
- **Challenges**
  - Learning GNN parameters with backprop
  - Sample expressions with greater diversity
- **Next Week**
  - Reach out to Xujie for early feedback
  - Progress committee formation
- **Reading**
  - [Syntax-Directed Variational Autoencoder for Structured Data](https://arxiv.org/pdf/1802.08786.pdf) (Dai et al., 2018)

## August 14, 2020

- **Last meeting**
  - Showed an eDSL with support for [notebook graphs](https://github.com/breandan/kaliningraph/blob/6fc7ca2e029b8a04c03993e77f3d41bd132654eb/notebooks/Program%20Graphs.ipynb)
- **Progress**
  - Read about logic/relational programming with [MiniKanren](http://minikanren.org/)
  - Met with [Torsten](http://tscholak.github.io/) about SQL question answering (guest lecture for [COMP 598](https://github.com/jin-guo/COMP598_Fall2020)?)
  - JuliaCon 2020 / [Reactive Notebooks](https://www.youtube.com/watch?v=IAF8DjrQSSk) + [Pluto.jl](https://github.com/fonsp/Pluto.jl)
- **Challenges**
  - Debugging the GNN implementation
- **Reading**
  - [Algebra and Machine Representation of Statistical Models](https://arxiv.org/abs/2006.08945)
  - [Autocompletion graphs](https://anvaka.github.io/vs/?query=)
- **Misc**
  - Confirmed TAship for COMP 698 / SE for Building Intelligent Systems
  - [LING 645: Computational Linguistics](https://foundations-computational-linguistics.github.io/)
  - Reviewed a [PR for sparse matrices](https://github.com/lessthanoptimal/ejml/pull/75)
  - Wrote a [roadmap](https://github.com/breandan/kotlingrad/issues/11#issuecomment-668345508) for differentiable SE

## August 7, 2020

Vacation.

## July 30, 2020

- **Last Week**
  - Demonstrated a Python-like eDSL + notebook interpreter
  - Graph computation proof-of-concept via integer matrix powering
  - Researching the [complexity](https://github.com/breandan/kotlingrad/issues/11#issuecomment-663378779) of subgraph matching and rewriting schemes for trees/DAGs/DGs
- **Progress**
  - Ported the [notebook eDSL](https://github.com/breandan/kaliningraph#computation-graph) into a [real notebook](https://github.com/breandan/kaliningraph/blob/master/notebooks/Hello%20Kaliningraph.ipynb)
  - Removed boundaries in order to support [inter-cell graphs](https://github.com/breandan/kotlingrad/blob/master/samples/notebooks/hello_kotlingrad.ipynb)
  - [Benchmark](https://github.com/breandan/kotlingrad/blob/master/core/src/test/kotlin/edu/umontreal/kotlingrad/perf/SparseTest.kt#L42) matrix powering to test graph-based execution scheme
  - Lowered the DSL onto a common graph-based intermediate representation
- **Challenges**
  - Expression simplification and subgraph pattern-matching is NP-hard in general
  - Identifying the novel contribution to our work. Staging to graph execution for imperative code?
  - No really good GPU-accelerated libraries for sparse graph representation right now. Build one?
  - Trying to avoid excessive yak-shaving, can optimize the runtime later
- **Next Week**
  - Demonstrate semantic similarity via graph embedding - similar code snippets should produce similar vectors
  - Plot similarity between similar code snippets on organic / synthetic code base
  - Finish writing up the summer summary and future research plans
- **Reading**
  - [Frequent Subgraph Analysis and its Software Engineering Applications](https://etd.ohiolink.edu/!etd.send_file?accession=case1496835753068605) - Wow! This is a real goldmine of graphs for software engineering applications.
  - [Relevant subgraph extraction from random walks in a graph](https://www.info.ucl.ac.be/~yde/Papers/kwalks_2006.pdf) - Efficient pattern matching would allow us to retrieve subgraphs in larger databases
  - [ScaNN: Efficient Vector Similarity Search](https://ai.googleblog.com/2020/07/announcing-scann-efficient-vector.html) - Nice demo of "locality-sensitive" hashing / retrieval - this fixes our TraceLink search problem (too slow to do KNN over entire dataset)
  - [Lambda Calculus and the Four Colour Theorem](http://noamz.org/talks/oasis-lam4ct.2018.06.22.pdf) - Some interesting connections between LC and topology

## July 23, 2020

- **Last Week**
  - Invariant analysis, model cards & notebook provenance
  - Selecting a use case to showcase the value of abstract interpretation
  - Getting a feel for how the algorithm works on real notebooks
- **Progress**
  - Built a proof-of-concept [notebook interpreter](https://github.com/breandan/kaliningraph#computation-graph)
  - Collected [developer feedback](https://news.ycombinator.com/item?id=23878381) on graph draft and research plans
  - Read about lambda calculus reductions
  - Implemented polymorphic inductive graph
- **Challenges**
  - Working out the execution model using matrix representation
  - Mapping invariants to symbolic values (e.g. Reps-style [propagation](https://youtu.be/wiYfS1aoAAg?t=1400))
  - Finding a stable linear algebra library for sparse graph representations
  - Identifying the right audience and feature prioritization
- **Next Week**
  - Evaluate notebook interpreter on real inputs using [Miller's evaluator](http://www.cs.cmu.edu/~glmiller/Publications/MRK86b.pdf)
  - Write up summer progress in a summary document for posterity
  - Prepare a JS demo for website to showcase the idea
- **Reading**
  - [The Program Dependence Graph and its Use for Optimization](https://www.cs.utexas.edu/~pingali/CS395T/2009fa/papers/ferrante87.pdf)
  - [The Symmetric Interaction Calculus](https://medium.com/@maiavictor/the-abstract-calculus-fe8c46bcf39c)
  - [Conversion of Units of Measurement](https://www.cs.utexas.edu/users/novak/units95.html)
  - [Semantic Grep: Lightweight static analysis](https://github.com/returntocorp/semgrep)
  - [Learning Graph Structure With A Finite-State Automaton Layer](https://arxiv.org/abs/2007.04929)

## July 16, 2020

- **Last Week**
  - [ICML](https://icml.cc/virtual/2020) and [RSS](https://roboticsconference.org/)
  - Feedback from notebooks meeting and research planning
  - Read about arithmetic circuit evaluation ([Miller, 1987](http://www.cs.cmu.edu/~glmiller/Publications/MRK86b.pdf)) and dataflow analysis ([Reps, 2017](https://research.cs.wisc.edu/wpis/papers/TOPLAS-00005-2016.R1.pdf))
- **Progress**
  - Built an [interactive debugger](https://github.com/breandan/kaliningraph#visualization) for labeled transition systems
  - Implemented some different algebraic graph algorithms
  - More [writing](http://breandan.net/2020/06/30/graph-computation/#graphs-computationally) and fleshing out research topics
- **Challenges**
  - Parsing Python into a common graph representation
  - What is the best way to handle variable sharing?
  - How does this align with common notebook use cases?
- **Next Week**
  - Try to incorporate some examples from the notebooks dataset
  - Implement WL embedding using our graph representation
  - Work on the notebooks survey a bit more, tie in the GRL stuff

## July 9, 2020

- **Last week**
  - MSR/ICSE/ML4SE/[MDS2020](https://github.com/johnrgilbert/MDS2020-linear-algebraic-graph-tools)
  - [GraphBlas](https://github.com/DrTimothyAldenDavis/GraphBLAS) pen source tools for graph computing
  - Looked into [Daikon](https://plse.cs.washington.edu/daikon/pubs/) / invariant detection
- **Progress**
  - Wrote a [blog post on graph computation](http://breandan.net/)
  - Implemented some visualizations for graphs
- **Challenges**
  - How to execute notebooks reliably
  - How to encode notebook graph as a matrix
- **Next Week**
  - Try to retrofit Pantograph into an existing notebook
  - Try graph embedding approach on some real notebooks
- **Reading**
  - [Sosed: a tool for finding similar software projects](https://arxiv.org/pdf/2007.02599.pdf) - Sub-token based project similarity detection on GitHub
  - [AI Feynman 2.0: Pareto-optimal symbolic regression exploiting graph modularity](https://arxiv.org/abs/2006.10782) - Tegmark's new symbolic regression work
  - [Graph-based, Self-Supervised Program Repair from Diagnostic Feedback -](https://arxiv.org/pdf/2005.10636.pdf) Nice idea for using compiler error messages to localize syntax errors
  - [Graph Algorithms in the Language of Linear Algebra](https://epubs.siam.org/doi/book/10.1137/1.9780898719918?mobileUi=0) - Most graph algorithms can be rewritten in LA


## June 25, 2020

- PEQ/CSQ bureaucracy
- Added [notebook support](https://github.com/breandan/kotlingrad/blob/master/samples/notebooks/hello_kotlingrad.ipynb) for Kotlingrad
- Minor revisions to survey
- Challenges
  - Is there a way to combine dynamic and static analysis techniques? [https://miasm.re/blog/2017/10/05/playing_with_dynamic_symbolic_execution.html](https://miasm.re/blog/2017/10/05/playing_with_dynamic_symbolic_execution.html)
  - Try to integrate with existing symbolic execution frameworks. Maybe Z3? [https://ericpony.github.io/z3py-tutorial/strategies-examples.htm](https://ericpony.github.io/z3py-tutorial/strategies-examples.htm)
- Reading/watchlist
  - Virtual PLDI - [links](https://github.com/breandan/dossier/blob/master/meetings/minutes.md#pldi-2020) to some talks and short summary
  - AKBC conference - saw an [interesting talk](https://youtu.be/fY4wAphy56w?t=2426) about [ChartDialog](http://nakashole.com/papers/2020-acl-charts.pdf)
  - Code generation for [typed dataframes](https://www.youtube.com/watch?v=YFtiDqYVhWY) with Kotlin notebooks
  - [Context-Free Path Querying by Matrix Multiplication](https://dl.acm.org/doi/pdf/10.1145/3210259.3210264) - Use matmuls to query a graph (also: subgraph matching is hard)
  - [Meta-modelling and graph grammars for multi-paradigm modelling in AToM3](https://idp.springer.com/authorize/casa?redirect_uri=https://link.springer.com/content/pdf/10.1007/s10270-003-0047-5.pdf%26casa_token=OU5DshcJECAAAAAA:hAbA6vAf98vRwqMttp29GUeqjZtQ4HPT7dPCuzecHmeHq3_FjB1sMT5VLXif4vVzl9sH1Pp4iIOl1tY1OA) (also: McGill had a [modeling lab](http://msdl.cs.mcgill.ca/)!? where did they all go?)
  - [Describing the syntax of programming languages using conjunctive and Boolean grammars](http://users.utu.fi/aleokh/papers/conj_bool_programming.pdf) - Trees as an algebraic abstraction for modeling code
  - [Parsing with zippers](https://github.com/pdarragh/parsing-with-zippers-paper-artifact) - like [PwD](https://arxiv.org/abs/1604.04695) but 15,600 times faster!
- Dentist meeting Friday

## June 18, 2020

- Migrated notebook survey to Overleaf
- Published [slicing demo](https://github.com/breandan/pantograph) to GitHub
- PLDI virtual conference
- Shopify presents [ShipIt! Presents: Understanding Programs Using Graphs in TruffleRuby](https://engineering.shopify.com/blogs/engineering/understanding-programs-using-graphs#Register)
- Clean up Pantograph a bit more
- Tidy up the notebook surveyebook survey to Overleaf
- Challenges/questions
  - Identifying and documenting the edge cases for static analysis in Python. Could be useful to collect.
  - Python seems pretty dynamic. Hard to cover all the cases. May be simplifying assumptions?
- Reading list:
  - [Fortress Language Specification](https://www.ccs.neu.edu/home/samth/fortress-spec.pdf) - Fortress is a notebook-friendly language for pseudocode-looking LaTeX. Interesting take on Documentation as code / Code as documentation
  - [Integrating Prose as First-Class Citizens with Models and Code](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.403.3869&rep=rep1&type=pdf) - Voelter brainstorming different approaches to literate programming.
  - [Staging notebook](https://ocamllabs.io/iocamljs/staging.html) - Introduces staged metaprogramming for runtime analysis (OCaml)
  - [Implicit Staging of EDSL Expressions](https://doi.org/10.1007/978-3-662-44202-9_16) - Interesting comparison between shallow and deep staging techniques.
  - [Penrose: From Mathematical Notation to Beautiful Diagrams](https://penrose.ink/media/Penrose_SIGGRAPH2020.pdf) - An interesting take on declarative programming and projectional editing
  - [Automata-Based Regex Matcher](https://scala-lms.github.io/tutorials/automata.html)

## June 11, 2020

- Wrote [notebooks outline](../research/notebooks.md)
- noworkflow debugging
- Did some research into provenance and workflow
- Comprehensive exam logistics (registering, syllabus, MoU, progress committee)
- PEQ reform / UdeM paperwork (due Wed.)
- Root canal on Thursday
- Challenges/questions
  -Is it possible to design a language-agnostic graph?
  -What is the downstream task we trying to support?
  -How do we identify semantically similar graphs?
- Reading list
  - [Hypermodern Python](https://cjolowicz.github.io/posts/hypermodern-python-01-setup/): Nice overview of modern Python development tools and techniques.
    - [typing](https://cjolowicz.github.io/posts/hypermodern-python-04-typing/) - mypy, pyre, pyright, pytype
    - [CI/CD](https://cjolowicz.github.io/posts/hypermodern-python-06-ci-cd/) - poetry
    - [documentation](https://cjolowicz.github.io/posts/hypermodern-python-05-documentation/) - sphinx, rst
  - [Towards a Framework for Generating Program Dependence Graphs from Source Code](https://dl.acm.org/doi/pdf/10.1145/3278142.3278144): PDGs are often used for provenance and workflow applications. Possible to construct using compiler IR.

## June 3, 2020

- Physics experiments: comparing LNN with GS
- Looked into TF4J/TVM4J and [multiplatform builds](https://github.com/apache/incubator-tvm/issues/5707#issuecomment-636966615)
- Looked into [dynamic slicing](https://dl.acm.org/doi/pdf/10.1145/93548.93576).
  - [Def-use and use-def chains](https://en.wikipedia.org/wiki/Use-define_chain)
  - Normally, dynamic slicing only records paths taken, but is there a way to recover statics?
  - Is the Python interpreter IR translation invertible? [Sort of](https://github.com/rocky/python-decompile3).
  - [Sometimes](https://bugs.python.org/issue33826) possible to [recover source code programmatically](https://pymotw.com/2/sys/tracing.html)
  - Possible to expand runtime paths to include alternate paths from source code.
  - This would allow us to "search" through the space of graphs at runtime
  - What are the differences between PDG/DFG/CFG/computation graphs
- Looked into discretionary/essential US/CA [border crossing scenarios](http://s3.documentcloud.org/documents/6935230/CBSA-Directives.pdf)
- Medical records release and transfer paperwork US/Canada
- Challenges/questions
  - Connecting information retrieval with notebook analysis
  - What are the similarities/differences between PDG/DFG/CFG/computation graphs?
  - How to formulate target as learning objective
- Reading List
  - [FaCoY – A Code-to-Code Search Engine](https://dl.acm.org/doi/pdf/10.1145/3180155.3180187) - Query expansion techniques for similar source code snippets.
  - [DéjàVu: A Map of Code Duplicates on GitHub](https://dl.acm.org/doi/pdf/10.1145/3133908) - Descriptive study on the incidence and prevelance of code duplication on GitHub.
  - [Understanding programs using graphs](https://engineering.shopify.com/blogs/engineering/understanding-programs-using-graphs) - Seaton advocates for the benefits of graph-based representation for program understanding.
  - [Programming As Theory Building (1985)](http://pages.cs.wisc.edu/~remzi/Naur.pdf) - Source code isn't the model. Human knowledge is the model. Naur makes the case for human-centered computing.
  - [Programming Languages, Natural Languages and Mathematics](https://doi.org/10.1145/361227.361229) - Naur on the poetry and science of language construction. Interesting discussion on descriptive vs. prescriptive linguistics.
  - [Computing Versus Human Thinking](https://dl.acm.org/doi/pdf/10.1145/1188913.1188922) - Naur's quasi-philosophical musings about cognition and computation. Seems a bit nebulous in hindsight.

## May 27, 2020
- Reboot progress notes on GitHub
- Write [research statement](../research/statement.md)
- Finalize IFT 6759 grades
- Meeting with Krishna et al. about physics
- [Registered](https://regmaster.com/2020conf/PLDI20/register.php) for PLDI (June 15-20)
- Looked into program slicing techniques
- Reading list
  - Program slicing techniques
  - Dawson Engler / KLEE / Coverity
  - symbolic execution / concolic testing
  - Z3 / SMT solving, Lean
  - rewriting systems (normalization, confluence)
  - [nbformat](https://nbformat.readthedocs.io/en/latest/)

## Nov. 20th, 2019
- Tooling [updates](https://github.com/acejump/TraceJump/tree/1bba53bd8b14e5b9717c0d25f9d7b7a72add1fe3) to TraceJump to support native installer
- Meeting with Awa Samake about RL environment
- Meeting with Sacha Lepretre about KAST/MILA collaboration
- Course work and writing reports

## Nov. 13th, 2019
- Started running experiments and writing the TraceJump research report
- Met with Liam and Michalis to discuss [jury feedback](https://github.com/breandan/kotlingrad/commit/5203acb73f8ee069d1735ca7b5b4635897902dfd) and corrections
- Submitted poster to AICan poster session
- UdeM/DIRO MSc Final thesis corrections due by February 6th

## Oct. 30th, 2019
- Homework for Prakash’s class
- Finish project proposal
- Lucene support for TraceJump

## Oct. 23, 2019
- Project [presentation for COMP 762](https://docs.google.com/presentation/d/1ccF94AJO6v5tejF0nzLtnxbQPnERyASOlHx8D8zqQ6I/edit?usp=sharing)
- Project [proposal for COMP 762](https://www.overleaf.com/project/5d9e5a280275d90001fc9929)
- Data wrangling and [search provider selection](https://github.com/acejump/TraceJump/commit/a88c25cfa981969ec614fe18c3929e082fdc608b) for TraceJump
- Released [update to AceJump](https://github.com/acejump/AceJump/blob/master/CHANGES.md#358) and [update to Hatchery](https://github.com/duckietown/hatchery/commit/0212438044941d562bdc204770b4c3e3f7b60be0)
- Submitted student volunteer application to [POPL](https://popl20.sigplan.org/)
- Thesis corrections and prepare for jury (convening Nov. 6th)

## Oct. 16, 2019
- Uncle Andy’s funeral / celebration of Life
- Data wrangling for COMP 762 class project
- Wrote a [differentiable Pendulum](https://github.com/breandan/kotlingrad/blob/master/src/main/kotlin/edu/umontreal/kotlingrad/samples/physics/SinglePendulum.kt)
- Kotlingrad [type system improvements](https://github.com/breandan/kotlingrad/commit/cc71fe2f37820cef9e0c0bff1b4472b3221fc8b1)
- Reviewed two PRs for AceJump: [#306](https://github.com/acejump/AceJump/pull/306), [#307](https://github.com/acejump/AceJump/pull/307)
- [Project proposal](http://conal.net/papers/essence-of-ad/essence-of-ad-icfp.pdf) for Prakash’s class

## Oct. 9, 2019
- SE Montreal Meeting on Friday
- Submitted to CHI as a student volunteer
- Made [TraceJump](https://github.com/acejump/tracejump) more [resource-friendly](https://github.com/acejump/TraceJump/commit/be6198624f123004d5c3f9eff2296a9c652b12f8)
- Planning for the COMP 762 [group project](https://www.overleaf.com/project/5d9e5a280275d90001fc9929)
- [Disintegration notes](https://www.overleaf.com/3927127945tprqwdxtkybs) for Prakash
- Facebook Fellowship grant application
- Registered and booked travel to NeurIPS


## Oct. 2, 2019
- COMP 599 Homework #2
- COMP 762 Project meeting
- Differentiable physics/rendering meeting with [Derek Nowrouzezahrai](http://www.cim.mcgill.ca/~derek/)
- Meeting with Violet, source code to ASTs
- Wrote [PTML Rebuttals](https://openreview.net/forum?id=SkluMSZ08H)
- [Parallelized](https://github.com/acejump/TraceJump/commit/940b917b8c75290ea1575aa50792aa6e9b09f60a) [TraceJump](https://github.com/acejump/tracejump) recognition loop
- Fixed an [issue](https://github.com/breandan/kotlingrad/issues/6) with [Kotlingrad](https://github.com/breandan/kotlingrad) package distribution.

## Sept. 25, 2019
- Worked on [paper presentation](https://slides.com/breandan/towards-an-intelligent-domain-specific-traceability-solution) for COMP 762
- Developed prototype for screen reader trace link prediction tool
- Started paper for [AAMAS submission](https://aamas2020.conference.auckland.ac.nz/area-topics-of-interest/##area2) (Deadline: Nov. 15th)
- Started paper for [PAKDD submission](https://www.pakdd2020.org/callforpapers.html) (Deadline: Nov. 25th)
- Preparing Math Bootcamp [blog post](https://math-bootcamp.github.io/machinelearning/basics/2019/07/23/the-derivative/) for release

## Sept. 18, 2019
- Mila Hackathon - Developed prototype for [OpenAI Gym Environment](https://github.com/breandan/gym-pc/)
- Submitted [abstract](https://github.com/breandan/kotlingrad/blob/master/latex/ptml/ptml_abstract.pdf) to [Program Transformations for ML](https://program-transformations.github.io/) workshop
- Discussion with [Thomas Schweizer](https://thomsch.github.io/) about research interests