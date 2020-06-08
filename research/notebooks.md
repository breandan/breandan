# Computational Notebooks

## Notebooks and REPLs

Computational notebooks are documents which allow developers to interact with a program's runtime environment by incorporating short snippets of code and text. This is similar to a [REPL, or language shell](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), commonly found in scripting languages. They can be used for both [exploratory and explanatory](https://doi.org/10.1145/3173574.3173606) purposes.

Some [popular computational notebooks](http://pgbovine.net/publications/computational-notebooks-design-space_VLHCC-2020.pdf) include:

* [Wolfram Notebook](https://www.wolfram.com/notebooks/)
* [Maple Workbook](https://www.maplesoft.com/)
* [Sage notebooks](https://doc.sagemath.org/html/en/thematic_tutorials/tutorial-notebook-and-help-long.html)
* [Jupyter Notebook](https://jupyter.org/) / [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/)
* [Google Colab](https://colab.research.google.com/notebooks/basic_features_overview.ipynb)
* [JetBrains Datalore](https://datalore.io/)
* [Apache Zepplin](https://www.cloudera.com/products/open-source/apache-hadoop/apache-zeppelin.html)

By far, Jupyter is the most popular computational notebook. Originally intended for Python, [most programming languages](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) now have Jupyter Notebook kernels. For now, we will use "notebooks" to refer to Jupyter notebooks.

![](https://miro.medium.com/max/1400/1*GVbyY-QSiwWewI1Nl2Bb1A.png)

## Notebooks and IDEs

Notebooks are beginning to incorporate functionality typically associated with an interactive development environments, such as [extensions](https://jupyterlab.readthedocs.io/en/stable/developer/extension_dev.html), code completion and static analysis tools.

## Notebooks and graphs

There are many types of [graphical representations](https://engineering.shopify.com/blogs/engineering/understanding-programs-using-graphs) for programs, such as:

* [Computational graphs](https://colah.github.io/posts/2015-08-Backprop/)
* [Dataflow graphs](https://en.wikipedia.org/wiki/Data-flow_analysis)
* [Control flow graphs](https://en.wikipedia.org/wiki/Control-flow_graph)
* [Program dependence graphs](https://en.wikipedia.org/wiki/Program_dependence_graph)
* [Call graphs](https://en.wikipedia.org/wiki/Call_graph)
* [Def/use chains](https://en.wikipedia.org/wiki/Use-define_chain)

There are also many projects which support the construction of these graphs:

* [noworkflow](https://github.com/gems-uff/noworkflow)
* [astminer](https://github.com/JetBrains-Research/astminer)
* [yesworkflow](https://github.com/yesworkflow-org/yw-prototypes)
* [burrito](https://github.com/pgbovine/burrito)

It would be convenient for debugging and reproducibility if it were possible for users to inspect the computation graph of a given notebook. These graphs can also be used to perform further analysis, e.g. graph embedding.

## Notebooks and reproducibility

One of issue which has troubled machine learning is the [reproducibility crisis](https://towardsdatascience.com/why-git-and-git-lfs-is-not-enough-to-solve-the-machine-learning-reproducibility-crisis-f733b49e96e8). We are primarily concerned with software reproducibility, i.e. What was the series of steps used to execute a given program and how can we reproduce those steps?

Many machine learning projects have difficulty managing this knowledge during the project lifecycle. It would be convenient if those steps were automatically recorded, without the user needing to think about them very much.

Many workflow engines have recently emerged in attempt to solve this problem, namely:

* [Apache Airflow](https://airflow.apache.org/)
* [DataBricks MLflow](https://airflow.apache.org/)
* [TensorFlow Extended](https://www.tensorflow.org/tfx)
* [GitHub workflow](https://help.github.com/en/actions/configuring-and-managing-workflows/configuring-a-workflow)

These all require the user to explicitly define a pipeline using a description language, graphical or command line interface.

Notebooks are essentially a form of data pipelining. One way to think of a notebook is as a pure function, which accepts some input, and produces some output. All data is captured as input and all side effects are captured as output. Each step performs some transformation over the input, producing a new output.

![](https://miro.medium.com/max/1342/1*IvmanLVx-Pcht4q31wd6Sw.png)

One way to accomplish this is to reify the entire program control state. This is called a [continuation](https://en.wikipedia.org/wiki/Continuation). Each statement represents some small transformation on that pipeline, and carries the entire program state along with it, allowing it to be suspended and resumed as needed.

## Notebooks and programming languages

Notebooks contain at least three languages:

* [Markdown](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html)
* [Notebook magic](https://ipython.readthedocs.io/en/stable/interactive/magics.html)
* Script language
* [Raw cell](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html?highlight=raw%20cell#raw-cells)

These grammars can be combined into a single language, using a [parser combinator](https://en.wikipedia.org/wiki/Parser_combinator).

## Notebooks and metaprogramming

> Programs must be written for people to read, and only incidentally for machines to execute. --Abelson and Sussman

Most [program translators](https://en.wikipedia.org/wiki/Translator_(computing)) are intended to support execution, and hence destroy source code during the translation process. This is unfortunate, as source code files are [structured documents](https://doi.org/10.1109/WPC.2002.1021351) which contain rich semantic information that describes the program's behavior.

It should be possible to fully reify the entire notebook (including comments, log statements, output figures, etc.) during compilation/interpretation. This information is available through the [notebook magic](https://ipython.readthedocs.io/en/stable/interactive/reference.html#input-caching-system), but could be programmatically available for introspection within the program runtime. This would allow notebook users to analyze the structure of the notebook, extract workflows and evaluate the

## Notebooks and information retrieval

Prior work has explored source code retrieval from graphical representations using e.g. the [WL similarity metric](https://davidbieber.com/post/2019-05-10-weisfeiler-lehman-isomorphism-test/):

- [Enriched Weisfeiler-Lehman Kernel for Improved Graph Clustering of Source Code](https://link.springer.com/chapter/10.1007/978-3-030-44584-3_20)
- [Detecting Similar Programs via the Weisfeiler-Leman Graph Kernel](https://www.martinschaef.de/papers/icsr2016.pdf)

While semantic similarity is undecidable in general, it would be helpful to identify similar cells in notebooks from a corpus of other notebooks. This either requires translating all documents to graphs, or synthesizing a regex query to retrieve plaintext documents.