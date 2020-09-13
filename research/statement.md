# Research Statement

I am a software engineer in the Software Technology Lab at McGill University, under the supervision of Jin Guo. There, I am building tools to help software engineers find information and reason about software, by learning to read and write code.

Program understanding is starting to show a number of practical applications for software engineering, e.g. code completion, static analysis, and information retrieval. My research seeks to aid humans designing and maintaining programs by helping them locate relevant information and manipulate the structure of connected software applications.

As a software engineer, I am particularly eager for the arrival of knowledge-enhanced and assistive programming tools. More concretely, my research attempts to infer relationships between software artifacts, including natural and formal languages, using machine learning. I believe there will be demand for such tools, if we can demonstrate their output is:

1. Contextually relevant
2. Sufficiently precise
3. Transparent / explainable

<!--Recent algorithms in language modeling and graph learning promise to deliver more specific suggestions while requiring fewer examples. My research focuses on translating theory into practice and maximizing user adoption, retention and satisfaction. There is a path to putting these algorithms into production, and my work studies how to best apply them to aid developers writing software in real world scenarios.-->

Today's development environments are growing smarter and more creative. They can perform many useful tasks for humans writing software, such as parsing, refactoring and navigation. Natural language processing is able to identify relevant documentation. Tools from machine learning and automated reasoning, we can analyze programs and identify potential conflicts. And using automated bug-fixing and program repair, we can synthesize code to correct logical errors. Together, humans and computers can work together to understand and debug complex information processing systems.

[![](../clipart/program_synthesis.png)](https://hal.archives-ouvertes.fr/hal-02190026/document#page=5)
![](https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2017/08/Relationship-between-Induction-Deduction-and-Transduction.png)
[![](../clipart/triangle.gif)](http://www.naur.com/comp/c1-1.html)

## Introduction

Our goal is to apply graphs to understand the relationships between natural and formal languages in software repositories. Software repositories contain a variety of file formats, each with varying grammar and implicit or explicit link structure. All of these documents are essentially graphs with additional structure (e.g. schema, labels).

## Program synthesis for knowledge systems

Program synthesis has a number of practical applications for knowledge systems. Here are three opportunities for designing better information retrieval systems:

### Query language

 First, is the query languages -- designing a language that supports efficient and expressive queries over a large dataset.

An invaluable skill of learning to code is learning to use Google and StackOverflow. These and most information retrieval systems which support a limited form of regular expression queries:

- Union
- Concatenation
- Kleene Star (maybe)

This language can take the form of a DSL in which the user provides certain examples. From the query, we can synthesize a program to fetch the results using classical techniques (e.g. Thompson / Glushkov).

### Structure and interpretation

Users need to be able to search over graph-structured objects in knowledge bases. Unfortunately subgraph isomorphism is NP-complete. Recent advancements in SAT/SMT solving have made NP-complete problems computationally tractable.

- Query expansion is possible using rule-based graph transformations.
- Knowledge graphs are graphs with "types" representing entities.
- Graph query languages can search over graphs, but not very efficiently.

What if we had extra computation to spend during the query? One way is to filter using a loose filter (e.g. fuzzy keyword indices or fixed-budget exploration budget on the knowledge graph), then run some state machine over the results, or to try to satisfy some logical properties, (like a type checker). We can use SAT solvers to do this!

### Context

What if we do not know the query? Where do queries come from? Context.

Suppose we have a document `D` and a term `T`, contained in that document. What does `T` mean? There are often other documents which explain `T`. Broadly, any document which explains `T` must contain `T`, and any document which contains `T`, tells us some information about its meaning. Sometimes, `T` is [polysemous](https://en.wikipedia.org/wiki/Polysemy), so not all documents which contain `T` may refer to the same entity. How do we recover all semantic occurrences of `T`?

Many documents contain links, which contain a term `T`, and reference another document. We could attempt to learn the target document directly, but such a mapping would not generalize well to out-of-vocabulary (OOV) tokens or out-of-distribution (OOD) graphs. Instead, we synthesize a query to find the document, by attending over the local context using a [selection based search](https://en.wikipedia.org/wiki/Selection-based_search).

### Content

Image understanding. Can perform OCR in images and search through them. For example, we demonstrate an application for searching through images:

* [TraceJump](https://github.com/acejump/TraceJump/)

### Interpretability

Most machine learning algorithms produce matrices as output. Matrices are not very interpretable. Some algorithms produce directed graphs as output (e.g. DARTS). These are also not very interpretable, but are structurally more similar to classical programs. Consider the space of program transformations: many programs are isomorphic under refactoring. We should prefer to generate those programs which more closely resemble human-written programs. Early work has shown we can use programs to learn, e.g. [formatting rules](https://dl.acm.org/doi/pdf/10.1145/2997364.2997383) and [code idioms](https://papers.nips.cc/paper/9265-program-synthesis-and-semantic-parsing-with-learned-code-idioms.pdf).

What is a convincing way to evaluate a programmer's ability? One way is to ask them to solve a problem by writing down some code. This task is arguably harder than the Turing Test (many human programmers fail the test every day). Another way is to write down a program and ask them what a program does when fed a certain input. This task is somewhat easier to solve, and there are many results suggesting the task may be tractable for neural networks to solve.

To learn programming, one must understand what a good program looks like (e.g. idioms and syntax), but also what a program does (denotational and operational semantics). This requires an understanding of how changes to code influences changes to execution. If we can learn a program to infer the behavior of another (e.g. short) program without executing it, this is a reasonable test of logical reasoning abilities. Neural networks are increasingly capable of performing simple variations this task.

## Roadmap

I believe that if we are going to teach machines to read and write code, we must take a principled approach grounded in computer science and start by learning very simple languages. Computer science has a rich literature in automata-based language learning. According to Chomsky, the simplest type of language is a regular language.

### Program synthesis

Much attention in program synthesis is devoted to the top of the [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy). While this approach directly translates into applied settings, there are many practical applications for less powerful languages. Instead, we start at the bottom, and work our way up.

- Synthesize a finite state automaton (regular)
- Use Angulin's L* algorithm as an oracle
- Use the finite state machine to search for relevant programs (i.e. suggest code)
- Synthesize a Buchi automaton (ω-regular)
- Synthesize a Pushdown automaton (context free)
- Synthesize an EPDA (tree-adjoining)
- Graph grammars / Graph rewrite systems
- Synthesize a Linear bounded automaton (context sensitive)

![](https://graphviz.gitlab.io/_pages/Gallery/directed/fsm.png)

There are a few strategies for selecting program synthesis tasks which have a good chance of yielding progress to learning methods. One strategy is to gather a human-labeled dataset (e.g. on GitHub), and perform supervised or semi-supervised or unsupervised learning on the source code using language modeling techniques.

Another strategy is selecting problems known to have exact solutions, but which are prohibitively expensive to deploy due to their computational complexity. This allows us to construct an oracle to verify the correctness of synthesized programs. Procedurally generating random instances provides an effectively unlimited training and validation set.

We propose a synthesis of the two strategies: in many cases, there are equivalent correct solutions with varying [descriptive complexity](https://en.wikipedia.org/wiki/Kolmogorov_complexity), in which case, we can use term rewriting to prioritize candidate solutions for [readability](https://web.eecs.umich.edu/~weimerw/p/weimer-issta2008-readability.pdf), [understandability](http://www.cs.kent.edu/~jmaletic/cs63902/Papers/Scalabrino17.pdf) or other soft metrics.

Program synthesizers must trade off the following criteria:

* Optimality: How accurate is the program / synthesizer?
* Efficiency: How efficient is the program / synthesizer?
* Readability: How readable is the program?

#### Optimality

We can imagine various metrics for measuring optimality:

* Test / Meta test error
* Bugs / Meta bugs rate
* Meta Precision / Recall

#### Efficiency

When comparing efficiency of two algorithms, we could use the following criteria:

* Wall clock time
* CPU temperature
* [Energy consumption](https://arxiv.org/abs/1906.02243)
* Profiler statistics (e.g. sampling- or instrumentation- based)
* Trace number of operations (e.g. FLOPS, MIPS & other benchmarks)

#### Readability

Although there are not many good metrics for code readability, it may be possible to quantify this metric using, e.g.:

* Cyclomatic / Halstead / McCabe complexity
* Checkstyle / pylint / pychecker
* Code smell detection
* Graph statistics on program dependence graph (e.g. degree/betweenness centrality
* Learned models?

## Agenda

In order to realize these goals, I must take the following concrete steps:

### Plan

- Write a query tool (Spring 2020)
- Write a notebook tool/survey (Summer 2020)
- Take qualifying exams (Winter 2021)
- Publish papers (3-5 papers)
- Write dissertation (2021-2023, est.)
- Graduate (2024, est.)

## Commitments

During my Ph.D., I am committed to pursuing the following activities:

### Teaching

- TA for IFT 6759 on applied ML (Spring 2020)
- TA for class on SE/ML (Fall 2020), pending

### Service

- Participate in research activities at KAST.
- Help out colleagues and lab mates.
- Contribute to open source.

