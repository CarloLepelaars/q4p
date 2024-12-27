![Python](https://img.shields.io/badge/python-3.10%2B-blue)
[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)

# q4p
Quantum Computing for (Python) Programmers

NOTE: This repository is a work in progress. Course entries are gradually added, updated and announced.

# Why this course?

There are excellent courses in Quantum Mechanics and Quantum Computing available on the Internet. Unfortunately, in my personal experience, many of the existing courses come with limitations:

1. Courses can be overly theoretical and mainly focused on the physics. This might resonate with people studying physics, but alienates programmers in general. The student often has to work through a lot of physics details before implementing something practical.
2. Courses offered by quantum computing companies often lock the student in to their own (Python) programming library/framework. Most of these libraries seem to be designed for physicists and do not leverage Python as a dynamic language. Quantum computing libraries are also generally not interoperable, so if you want to try out a different framework you have to learn the intricacies and syntax of that framework. Often the quantum circuits you made cannot be converted easily converted to another framework.

It seems to me many people are interested in quantum computing, but:

1. Don't know where to start.
2. Feel they are not smart enough to do quantum computing.
3. Think they have to do a lot of physics.

This course aims to remove those doubts and give you the confidence to do quantum computing. We will approach quantum computing from the perspective of a Python programmer. In the Python world we often want to iterate fast, distill complex problems to its essence and make use of the dynamic nature of the language to solve problems efficiently in a simple way. By learning from and playing with these series of notebooks you will be able to build your own quantum circuits from scratch. We will even discuss converting these quantum circuits to other quantum computing frameworks automatically so you can run circuits on real quantum computers from different (cloud) providers.

The essence of quantum computing and quantum information theory can be well understood with basic linear algebra and probability theory concepts. This course assumes you have some familiarity with these topics. Therefore this course is especially well suited for data scientists. Data scientists are generally used to iterate fast in Jupyter Notebooks, use Python as a dynamic language and are familiar with vector-matrix multiplication. Quantum computing involves complex numbers (i.e. imaginary numbers), but you definitely don't have to be an expert in them. For solving practical problems, we can mainly focus on linear algebra and probability theory concepts.

Hope you are excited to learn more about quantum computing! The next notebook will discuss how to work with qubits and we will build our first quantum circuit.

# Dependencies

This notebook series involves very few dependencies, so they will generally be pip installed in the notebook. 

We provide a `pyproject.toml` in case you would like to pre-install the dependencies.

## With uv (recommended)

To install dependencies for the `qcforp` notebooks with `uv`:

```bash
pip install uv
uv sync
```

You can now use `.venv` as a kernel in your Jupyter notebooks.
