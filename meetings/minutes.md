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
  - Look into literature: Kate Stole? Crista Lopez
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