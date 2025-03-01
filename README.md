# q4p

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)

[![q4p](q4p.png)](https://carlo.ai/q4p)

Quantum Computing for (Python) Programmers

NOTE: This repository is a work in progress. Course entries are gradually added, updated and announced.

> *q4p is a free course focused on applied quantum computing. If you would like to solve practical problems with quantum computing, this course is for you! No physics background required!*

> ⚡ **Get started**  
> Start with lesson 0b now! 
> - [Github](https://github.com/CarloLepelaars/q4p/blob/main/nbs/00b-marbles.ipynb)
> - [Kaggle](https://www.kaggle.com/code/carlolepelaars/q4p-00b-marbles-high-level-overview)
>
> A full overview of course entries is available at [carlo.ai/q4p](https://carlo.ai/q4p#main-course-entries).

# Why this course?

There are excellent courses in Quantum Mechanics and Quantum Computing available on the Internet. Unfortunately, in my personal experience, many of the existing courses come with limitations:

1. Courses can be overly theoretical and mainly focused on the physics. This might resonate with people studying physics, but alienates programmers in general. The student often has to work through a lot of physics details before implementing something practical.
2. Courses offered by quantum computing companies often lock the student in to their own (Python) programming library/framework. Most of these libraries seem to be designed for physicists and do not leverage Python as a dynamic language. Quantum computing libraries are also generally not interoperable, so if you want to try out a different framework you have to learn the intricacies and syntax of that framework. Often the quantum circuits you made cannot be converted easily converted to another framework.

It seems to me many people are interested in quantum computing, but:

1. Don't know where to start.
2. Feel they are not smart enough to do quantum computing.
3. Think they have to do a lot of physics.

This course aims to remove those doubts and give you the confidence to do quantum computing. We will approach quantum computing from the perspective of a Python programmer. In the Python world we often want to iterate fast, distill complex problems to its essence and make use of the dynamic nature of the language to solve problems efficiently in a simple way. By learning from and playing with these series of notebooks you will be able to build your own quantum circuits from scratch. We will even discuss converting these quantum circuits to other quantum computing frameworks automatically so you can run circuits on real quantum computers from different (cloud) providers.

# Is this course for me?

The essence of quantum computing and quantum information theory can be well understood with **basic linear algebra and probability theory** concepts. This course assumes you have some familiarity with these topics. 

This course is especially well suited for data scientists. Data scientists are generally used to iterate fast in Jupyter Notebooks, use Python as a dynamic language and are familiar with vector-matrix multiplication. Quantum computing involves **complex numbers** (i.e. imaginary numbers), but you definitely don't have to be an expert in them. If you feel like you need more background on the basics, check out the [basics notebooks](https://carlo.ai/q4p#basics-entries) to get up to speed quickly.

This course uses solely open source software like [NumPy](https://numpy.org) and [Plotly](https://plotly.com). All the essential build blocks are packaged in the [skq](https://github.com/CarloLepelaars/skq) library so we are free to explore, build and tinker with quantum algorithms. To run our algorithms on real quantum computers [skq](https://github.com/CarloLepelaars/skq) offers functionality to convert to popular quantum frameworks like [Qiskit](https://github.com/Qiskit/qiskit), [Pennylane](https://github.com/PennyLaneAI/pennylane) and [OpenQASM](https://openqasm.com/intro.html).

[NumPy](https://numpy.org) works best as a foundational linear algebra library, because quantum algorithms can be easily simulated in it. This provides a playground where we can gain a solid understanding of how quantum algorithms work and analyze them. 

[skq](https://github.com/CarloLepelaars/skq) is built on NumPy and provides us the glue to convert our quantum circuits to whatever quantum framework we prefer. Cloud quantum computing providers often force us to use their Python library, so conversion of quantum circuits is essential. `skq` provides this glue and avoids us getting locked in to one specific quantum cloud provider.


Hope you are excited to learn more about quantum computing! In lesson 0b we will first look at a top-down overview of solving an unstructured search problem with a quantum algorithm called Grover's algorithm. In lesson 1 we dive into the details of how a qubit works and how to build quantum algorithms yourself.

# Why Quantum Computing?

Quantum Computing is a fascinating computing paradigm still in its infancy. You could say the field of Quantum Mechanics pre-dates Artificial Intelligence, but (to the best of my knowledge) people only started working on quantum as a basis for computation in the early 1970s. One of the seminal papers was written by [Richard Feynman in 1982](https://s2.smu.edu/~mitch/class/5395/papers/feynman-quantum-1981.pdf). This paper proposed a conjecture that quantum systems require quantum computers to be simulated efficiently, which was proved by [Seth Lloyd in 1996](https://fab.cba.mit.edu/classes/862.22/notes/computation/Lloyd-1996.pdf). This has huge implications as many systems in nature are quantum systems. There is strong evidence that quantum algorithms can perform some tasks faster than can ever be achieved on a classical computer.

Many problems in physics, materials science, chemistry and drug discovery have to deal with quantum systems and simulating these systems on classical computers requires huge amounts of compute. Besides the physical world, there are also core computer science problems that can benefit greatly from quantum computing. The main research areas here are [search](https://en.wikipedia.org/wiki/Grover%27s_algorithm), where quantum can provide a quadratic speedup, and [cryptography/factoring](https://en.wikipedia.org/wiki/Shor%27s_algorithm), where speedups can be exponential. For a detailed discussion of which problems quantum computers excel at, check out [this video](https://www.youtube.com/watch?v=33QmsXhIlpU).

Quantum computing has 3 main features that are not available on classical computers:

1. **Superposition:** Superposition is the mechanism that allows quantum computers to represent distributions of classical states. This allows for a new paradigm to think about parallel computation. While classical bits can only be in a 0 or 1 state, a quantum bit (qubit) can have values between 0 and 1. These intermediate values can be described as a probability distribution of obtaining a 0 or 1. It is therefore sometimes said that the quantum computer's memory can have many classical states "at the same time".
2. **Interference:** Quantum computation allows superpositions to interact, similar to how waves can amplify each other or cancel each other out. This also adds a mechanism for powerful parallel computation which can be leveraged to obtain potentially exponential speedups over classical algorithms. An example of the power of interference is the Quantum Fourier Transform used in [Shor's algorithm](https://en.wikipedia.org/wiki/Shor%27s_algorithm).
3. **Entanglement:** Entanglement is the phenomenon where multiple qubits can become correlated to each other in a way not possible on a classical computer. The amount of correlation can vary from completely uncorrelated to perfectly correlated. A quantum computer can also get entangled with its environment, a phenomenon called [quantum decoherence](https://en.wikipedia.org/wiki/Quantum_decoherence). In quantum computers this is often an unwanted side effect and is mitigated by [quantum error correction](https://en.wikipedia.org/wiki/Quantum_error_correction). Error correction plays an important part in unlocking the full potential of quantum computing.

# What you will learn

After working through the complete course you will have learned to:

- Gain a deep understanding of how qubits work and how to manipulate them to solve practical problems:
    - Quadratic speedups for unstructured search problems (i.e. Grover's algorithm)
    - Exponential speedups by leveraging the Quantum Fourier Transform (i.e. Shor's algorithm)
    - Solving general optimization problems with quantum algorithms (QAOA, QUBO, Ising models, Quantum Machine Learning, etc.)
    
- How to convert your quantum circuits to popular quantum frameworks and run them on real quantum computers (Qiskit, Pennylane, OpenQASM)
- Error correction techniques to make quantum algorithms more reliable.
- Analyze how quantum computations work and learn to implement them from scratch.

Techniques covered (you will learn the meaning of these terms soon):
- Qubits and Qudits
- Single and multi-qubit gates (Pauli gates, Clifford gates, Controlled gates, etc.)
- Bell states (Phi Plus, Phi Minus, Psi Plus, Psi Minus)
- The query model of computation
- Deutsch-Jozsa algorithm (determining if a function is constant or balanced)
- Grover's algorithm (unstructured search)
- Shor's algorithm (prime factorization using phase estimation and the Quantum Fourier Transform (QFT))
- Quantum software libraries (Qiskit, Pennylane, OpenQASM)
- Density matrices and channels (Quantum information theory)
- Quantum graph algorithms (Max-Cut, Traveling Salesman Problem)
- Quantum machine learning (Quantum Kernel Methods)
- Quantum error correction (Pauli Twirling, 9-qubit Shor code, 7-qubit Steane code)
- Quantum hardware (Photonic, Trapped Ions, Superconducting (Transmon Qubits), Topological (Majorana-based))

# How to get started

All the course notebooks can be viewed through [Github](https://github.com/CarloLepelaars/q4p/tree/main/nbs) or [Kaggle](https://www.kaggle.com/carlolepelaars/code?orderBy=dateUpdated&query=q4p+-). The notebooks do not have many dependencies and are lightweight if you would to run them on your own computer. Check out [carlo.ai/q4p](https://carlo.ai/q4p#main-course-entries) for an overview of every lesson with links.


# Dependencies

This notebook series involves very few dependencies, so they will generally be pip installed in the notebook. This series is also offered as [Kaggle Notebooks](https://www.kaggle.com/search?q=q4p+-+in%3Anotebooks), which can be forked and explored out of the box.

We provide a `pyproject.toml` in case you would like to pre-install dependencies.

To install dependencies for the `q4p` notebooks with `uv`:

```bash
pip install uv
uv sync
```

You can now use `.venv` as a kernel in your Jupyter notebooks.

## skq

Some notebooks will make use of the [skq](https://github.com/CarloLepelaars/skq) library, a Python library made for exploring quantum computing and quantum information theory.
