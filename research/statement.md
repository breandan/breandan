# Research Statement

I am a software engineer in the KAST lab at McGill University, under the supervision of Jin Guo. There, I am building tools to help software engineers find information and reason about software, by learning to read and write code.

Statistical learning is starting to show a number of [practical applications](#practical-applications) for software engineering, e.g. code completion, static analysis, and information retrieval. My research seeks to aid humans designing and maintaining programs by helping them locate information and manipulate the structure of connected software applications.

As a software engineer, I am particularly eager for the arrival of knowledge-enhanced and assistive programming tools. More concretely, my research attempts to infer relationships between software artifacts, including natural and formal languages, using machine learning. I believe there will be demand for such tools, if we can demonstrate their output is:

1. Contextually relevant
2. Sufficiently precise
3. Transparent / explainable

Recent algorithms in language modeling and graph representation learning promise to deliver more specific suggestions while requiring fewer examples. My research focuses on translating theory into practice and maximizing user adoption, retention and satisfaction. There is a path to putting these algorithms into production, and my work studies how to best apply them to aid developers writing software in real world scenarios.

Today's programming environments are becoming smarter and more creative. They can perform many useful tasks for humans writing software. Using static analysis and natural language processing, we can identify relevant documentation for programmers. Using tools from machine learning and automated reasoning, we can analyze programs and identify potential conflicts. And using automated bug fixing and program repair, we can synthesize code to correct logical errors. Together, humans and computers can work together to understand and debug complex information processing systems.

## Introduction

Graphs are general-purpose data structures used to represent many data types and procedural phenomena. All the following are examples of graphs, with increasing generality:

- **Sets**: data, multisets, posets, symbols
- **Sequences**: Lists, strings, traces, linear function composition
- **Trees**: [Abstract syntax trees](https://en.wikipedia.org/wiki/Abstract_syntax_tree), [document object model](https://en.wikipedia.org/wiki/Document_Object_Model), [phylogenic trees](https://en.wikipedia.org/wiki/Phylogenetic_tree), [decision trees](https://en.wikipedia.org/wiki/Decision_tree)
- **DAGs**: [Git](https://eagain.net/articles/git-for-computer-scientists/), [control flow](https://en.wikipedia.org/wiki/Control-flow_graph), [citation networks](https://en.wikipedia.org/wiki/Citation_network)
- **Directed graphs**: [State machines](https://en.wikipedia.org/wiki/Finite-state_machine), [lambda calculus](http://dkeenan.com/Lambda/), [web pages](https://computersciencewiki.org/index.php/The_web_as_a_directed_graph), neural networks
- **Hypergraphs**: [Zettelkasten](https://zettelkasten.de/), [categories](https://en.wikipedia.org/wiki/Category_theory), [the universe](https://writings.stephenwolfram.com/2020/04/finally-we-may-have-a-path-to-the-fundamental-theory-of-physics-and-its-beautiful/)

Graphs are often used to represent mathematical notation as I show in [Kotlin∇](https://github.com/breandan/kotlingrad). Graphs can also be used to represent other programming languages, including source code, intermediate representations and markup languages.

Graphs are also used to model natural language, including [constituency](https://en.wikipedia.org/wiki/Phrase_structure_grammar) and [dependency grammars](https://en.wikipedia.org/wiki/Dependency_grammar), [link grammars](https://en.wikipedia.org/wiki/Dependency_grammar) and other syntactic and semantic relationships between natural language entities.

![](https://upload.wikimedia.org/wikipedia/commons/8/8e/Thistreeisillustratingtherelation%28PSG%29.png)

[Knowledge graphs](https://arxiv.org/pdf/2003.02320.pdf) are another important type of graph structure used to represent relations between concepts, e.g. on wikis and other web based content management systems.

Our goal is to apply graphs to understand the relationships between natural and formal languages in software repositories. Software repositories contain a variety of file formats, each with varying grammar and implicit or explicit link structure. All of these documents are essentially graphs with different schema and labels.

## Roadmap

I believe that if we are going to teach machines to read and write code, we must start by learning very simple languages. According to Noam Chomsky, the simplest type of language is a regular language.

### Program synthesis

Much attention in program synthesis concentrates at the top of the [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy). While this approach directly translates into applied settings, there are many practical applications for less powerful languages. Instead, we start at the bottom, and work our way up.

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

It is our belief that successful applications of program synthesis must balance the following criteria:

* Optimality
* Efficiency
* Readability

## Practical Applications

Program synthesis has a number of practical applications for software engineering. Here are two possible examples:

### Information retrieval

An invaluable skill of learning to code is learning to use Google and StackOverflow. These and most other information retrieval systems support regular language queries.

- Union
- Concatenation
- Kleene Star (maybe)

From the query, we can synthesize a program to fetch the results using classical techniques (e.g. Thompson / Glushkov).

What if we do not know the query? Where do queries come from? Context.

Suppose we have a document `D` and a term `T`, contained in that document. What does `T` mean? There are often other documents which explain `T`. Broadly, any document which explains `T` must contain `T`, and any document which contains `T`, tells us some information about its meaning. Sometimes, `T` is [polysemous](https://en.wikipedia.org/wiki/Polysemy), so not all documents which contain `T` may refer to the same entity. How do we recover all semantic occurrences of `T`?

Many documents contain links, which contain a term `T`, and reference another document. We could attempt to learn the target document directly, but such a mapping would not generalize well to out-of-vocabulary (OOV) tokens or out-of-distribution (OOD) graphs. Instead, we synthesize a query to find the document, by attending over the local context. Queries are simple programs.

<!--### Program analysis-->

<!----TODO---->

### Interpretability

Most machine learning algorithms produce matrices as output. Matrices are not very interpretable. Some algorithms produce directed graphs as output (e.g. DARTS). These are also not very interpretable, but are structurally more similar to classical programs. Considering program transformations, many programs are isomorphic under refactoring. We should prefer those which more closely resemble human-written programs. We can use programs to learn, e.g. [formatting rules](https://dl.acm.org/doi/pdf/10.1145/2997364.2997383) and [code idioms](https://papers.nips.cc/paper/9265-program-synthesis-and-semantic-parsing-with-learned-code-idioms.pdf).

What is a convincing way to evaluate a programmer's ability? One way is to ask them to solve a problem by writing down some code. This task is arguably harder than the Turing Test. Many human programmers fail the test every day. Another way, is to write down a program and ask them what a program does when fed a certain input. This task is somewhat easier to solve, and there are early results suggesting the task may be tractable for neural networks to solve.

To learn programming, one must understand what a good program looks like (e.g. idioms and syntax), but also what a program does (denotational and operational semantics). This requires an understanding of how changes to code influences changes to execution. If we can learn to infer the behavior of a program without executing it, many would consider this a good indicator of logical reasoning abilities. Neural networks are increasingly capable of performing simple variations this task.

## Agenda

In order to realize these goals, I must take the following concrete steps:

### Plan

- Write a query tool (Spring 2020)
- Write a notebook tool (Summer 2020)
- Take qualifying exams (Fall/Winter 2020)
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

## References

