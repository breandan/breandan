# Research Statement

I am a software engineer at McGill University under the supervision of Jin Guo. During my Ph.D. studies, I want to build a tool to help software engineers find information and reason about software, by learning to read and write code.

## Introduction

Graphs are general purpose data structures which are used to represent many interesting concepts. All of the following things are graphs:

- Sets: data, multisets, posets, symbols
- Sequences: Lists, strings, traces, linear function composition
- Trees: Abstract syntax trees, [document object model](https://en.wikipedia.org/wiki/Document_Object_Model), phylogeny
- DAGs: [Git](https://eagain.net/articles/git-for-computer-scientists/), [control flow](https://en.wikipedia.org/wiki/Control-flow_graph), citation networks
- Directed graphs: [State machines](https://en.wikipedia.org/wiki/Finite-state_machine), [knowledge graphs](https://en.wikipedia.org/wiki/Knowledge_Graph), [lambda calculus](http://dkeenan.com/Lambda/), web pages, neural networks
- Hypergraphs: [Zettelkasten](https://zettelkasten.de/), [categories](https://en.wikipedia.org/wiki/Category_theory), [the universe](https://writings.stephenwolfram.com/2020/04/finally-we-may-have-a-path-to-the-fundamental-theory-of-physics-and-its-beautiful/)

Graphs can be used to represent mathematical notation as I show in Kotlin∇. Graphs can also be used to represent programs.

Today's computers are becoming smarter and more creative. They can perform many useful tasks for humans writing software.

## Roadmap

I believe that if we are going to teach machines to write code, they must start by learning very simple programs. According to Noam Chomsky, the simplest type of program is a finite state machine.

- Synthesize a finite state machine (NFA/DFA)
- Use Angulin's L* algorithm as an oracle
- Use the finite state machine to search for relevant programs (i.e. suggest code)
- Synthesize a Buchi automaton
- Synthesize a Pushdown automaton
- Synthesize a Linear bounded automaton
- ?

## Where are we today?

---Describe results of current project---

## Practical Applications

Besides code completion, program synthesis has three good applications, including:

### Information retrieval

An essential skill of learning to code is learning to Google. All information retrieval systems support regular language queries.

- Union
- Concatenation
- Kleene Star (maybe)

From the query, we can synthesize a program to fetch the results using classical techniques (e.g. Thompson / Glushkov).

What if we do not know the query? Where do queries come from? Context.

### Program analysis

--TODO--

### Interpretability

Most machine learning algorithms produce matrices as output. Matrices are not very interpretable. Some algorithms produce directed graphs as output (e.g. DARTS). These are also not very interpretable.

We can use programs to make information processing systems more interpretable.

To learn to program, we need to learn what a program looks like (e.g. idioms and syntax), but also what a program means (denotational and operational semantics).

### Parsing

Learn to parse from examples.

## Research Agenda

### The Plan

- Write a query tool
- Write a notebook tool
- Write a simple debugger
- Take qualifying exams (Fall/Winter 2020)
- Publish papers
- Write dissertation
- Graduate

## Commitments

### Teaching

- TA for class on applied ML (Spring 2020).
- TA for class on SE/ML (Fall 2020).

### Service

- Participate in research activities at KAST.
- Help out lab mates.

### Research

- Notebooks
- Automata


