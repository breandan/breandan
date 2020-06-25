## June 25

- PEQ/CSQ bureaucracy
-   Added [notebook support](https://slack-redir.net/link?url=https%3A%2F%2Fgithub.com%2Fbreandan%2Fkotlingrad%2Fblob%2Fmaster%2Fsamples%2Fnotebooks%2Fhello_kotlingrad.ipynb&v=3) for Kotlingrad
-   Minor revisions to survey
- Challenges
    -   Is there a way to combine dynamic and static analysis techniques? [https://miasm.re/blog/2017/10/05/playing_with_dynamic_symbolic_execution.html](https://slack-redir.net/link?url=https%3A%2F%2Fmiasm.re%2Fblog%2F2017%2F10%2F05%2Fplaying_with_dynamic_symbolic_execution.html&v=3)
    -   Try to integrate with existing symbolic execution frameworks. Maybe Z3? [https://ericpony.github.io/z3py-tutorial/strategies-examples.htm](https://slack-redir.net/link?url=https%3A%2F%2Fericpony.github.io%2Fz3py-tutorial%2Fstrategies-examples.htm&v=3)
- Reading/watchlist
    - Virtual PLDI - [links](https://slack-redir.net/link?url=https%3A%2F%2Fgithub.com%2Fbreandan%2Fdossier%2Fblob%2Fmaster%2Fmeetings%2Fminutes.md%23pldi-2020&v=3) to some talks and short summary
    - AKBC conference - saw an [interesting talk](https://slack-redir.net/link?url=https%3A%2F%2Fyoutu.be%2FfY4wAphy56w%3Ft%3D2426&v=3) about [ChartDialog](https://slack-redir.net/link?url=http%3A%2F%2Fnakashole.com%2Fpapers%2F2020-acl-charts.pdf&v=3)
    - Code generation for [typed dataframes](https://slack-redir.net/link?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DYFtiDqYVhWY&v=3) with Kotlin notebooks
    - [Context-Free Path Querying by Matrix Multiplication](https://slack-redir.net/link?url=https%3A%2F%2Fdl.acm.org%2Fdoi%2Fpdf%2F10.1145%2F3210259.3210264&v=3) - Use matmuls to query a graph (also: subgraph matching is hard)
    - [Meta-modelling and graph grammars for multi-paradigm modelling in AToM3](https://slack-redir.net/link?url=https%3A%2F%2Fidp.springer.com%2Fauthorize%2Fcasa%3Fredirect_uri%3Dhttps%3A%2F%2Flink.springer.com%2Fcontent%2Fpdf%2F10.1007%2Fs10270-003-0047-5.pdf%26casa_token%3DOU5DshcJECAAAAAA%3AhAbA6vAf98vRwqMttp29GUeqjZtQ4HPT7dPCuzecHmeHq3_FjB1sMT5VLXif4vVzl9sH1Pp4iIOl1tY1OA&v=3) (also: McGill had a [modeling lab](https://slack-redir.net/link?url=http%3A%2F%2Fmsdl.cs.mcgill.ca%2F&v=3)!? where did they all go?)
    - [Describing the syntax of programming languages using conjunctive and Boolean grammars](https://slack-redir.net/link?url=http%3A%2F%2Fusers.utu.fi%2Faleokh%2Fpapers%2Fconj_bool_programming.pdf&v=3) - Trees as an algebraic abstraction for modeling code
- Dentist meeting Friday

## June 18, 2020

-   Migrated notebook survey to Overleaf
-   Published [slicing demo](https://github.com/breandan/pantograph) to GitHub
-   PLDI virtual conference
-   Shopify presents [ShipIt! Presents: Understanding Programs Using Graphs in TruffleRuby](https://slack-redir.net/link?url=https%3A%2F%2Fengineering.shopify.com%2Fblogs%2Fengineering%2Funderstanding-programs-using-graphs%23Register&v=3)
-   Clean up Pantograph a bit more
-   Tidy up the notebook surveyebook survey to Overleaf
-   Challenges/questions
    - Identifying and documenting the edge cases for static analysis in Python. Could be useful to collect.
    - Python seems pretty dynamic. Hard to cover all the cases. May be simplifying assumptions?
-   Reading list:
    - [Fortress Language Specification](https://www.ccs.neu.edu/home/samth/fortress-spec.pdf&v=3) - Fortress is a notebook-friendly language for pseudocode-looking LaTeX. Interesting take on Documentation as code / Code as documentation
    - [Integrating Prose as First-Class Citizens with Models and Code](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.403.3869&rep=rep1&type=pdf) - Voelter brainstorming different approaches to literate programming.
    - [Staging notebook](https://ocamllabs.io/iocamljs/staging.html&v=3) - Introduces staged metaprogramming for runtime analysis (OCaml)
    - [Implicit Staging of EDSL Expressions](https://slack-redir.net/link?url=https%3A//doi.org/10.1007/978-3-662-44202-9_16&v=3) - Interesting comparison between shallow and deep staging techniques.
    - [Penrose: From Mathematical Notation to Beautiful Diagrams](https://penrose.ink/media/Penrose_SIGGRAPH2020.pdf&v=3) - An interesting take on declarative programming and projectional editing
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
    - [Hypermodern Python](https://slack-redir.net/link?url=https%3A%2F%2Fcjolowicz.github.io%2Fposts%2Fhypermodern-python-01-setup%2F&v=3): Nice overview of modern Python development tools and techniques.
        -   [typing](https://slack-redir.net/link?url=https%3A%2F%2Fcjolowicz.github.io%2Fposts%2Fhypermodern-python-04-typing%2F&v=3) - mypy, pyre, pyright, pytype
        -   [CI/CD](https://slack-redir.net/link?url=https%3A%2F%2Fcjolowicz.github.io%2Fposts%2Fhypermodern-python-06-ci-cd%2F&v=3) - poetry
        -   [documentation](https://slack-redir.net/link?url=https%3A%2F%2Fcjolowicz.github.io%2Fposts%2Fhypermodern-python-05-documentation%2F&v=3) - sphinx, rst
    - [Towards a Framework for Generating Program Dependence Graphs from Source Code](https://slack-redir.net/link?url=https%3A%2F%2Fdl.acm.org%2Fdoi%2Fpdf%2F10.1145%2F3278142.3278144&v=3): PDGs are often used for provenance and workflow applications. Possible to construct using compiler IR.

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