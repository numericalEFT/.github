# Numerical Effective Field Theory

Differentiable numerical framework for effective field theory in quantum many-body systems.

[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://numericalEFT.github.io/NumericalEFT.jl/)
[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://numericalEFT.github.io/NumericalEFT.jl/)
[![Build Status](https://github.com/numericalEFT/NumericalEFT.jl/workflows/CI/badge.svg)](https://github.com/numericalEFT/NumericalEFT.jl/actions)
[![codecov](https://codecov.io/gh/numericalEFT/NumericalEFT.jl/branch/master/graph/badge.svg?token=OKnDPEC3In)](https://codecov.io/gh/numericalEFT/NumericalEFT.jl)

## Why We Create this Package

Our package offers advanced numerical solutions for nonlocal effective field theory (EFT), a powerful method for understanding the behavior of large groups of quantum particles. EFT is widely utilized in various areas of modern physics such as nuclear, condensed matter and material science, but its conventional form, which relies on the principle of locality and high symmetries, can limit its effectiveness in real-world condensed matter systems where symmetries are broken and interactions are long-range and dynamic. An example of this type of nonlocal EFT is the description of valence electrons in normal metals, where the electron fields move in a lattice potential that breaks translational and rotational symmetry and the Coulomb interaction between electrons has a complex spacetime configuration. These types of EFT are notoriously challenging to solve. Our package offers cutting-edge numerical tools to solve nonlocal EFT, providing a new way to model real-world quantum many-body problems and opening new possibilities in various fields.

## Features

The package ``NumericalEFT.jl`` is a collection of several independent components, which are organized in the following infrastructure: 

![NumericalEFT](profile/assets/numericalEFT_clickable.svg)

Most of the components have been published as independent packages, and you can test or use them separately. The packages are still fast-evolving, but many are production-ready.

### Core packages: a set of self-contained and general-purpose tools.

- [Lehmann.jl](https://github.com/numericalEFT/Lehmann.jl): Discrete Lehmann representation (DLR) for imaginary-time/Matsubara frequency Green's function. For a generic Green's function at a temperature T, DLR is capable of representing it up to a given accuracy ϵ with a cost ~ log(1/T)log(1/ϵ), significantly cheaper than a naive approach with a cost ~ 1/(Tϵ). 

- [FeynmanDiagram.jl](https://github.com/numericalEFT/FeynmanDiagram.jl): A mini-compiler that compiles generic multi-loop Feynman diagrams to a computational graph, which then can be efficiently manipulated or evaluated. The same type of computational graph has been a cornerstone of the neural-network-based machine learning.

- [MCIntegration.jl](https://github.com/numericalEFT/MCIntegration.jl): An adaptive Monte Carlo calculator for general high dimensional integral. It is one of the most robust and fastest Monte Carlo integration packages on the market. 

- [CompositeGrids.jl](https://github.com/numericalEFT/CompositeGrids.jl): Composite Cheybeshev/Gaussian/logarithmic grid systems for highly efficient one-dimensional interpolation and integration. It allows the user to combine different grids to represent nontrivial functions.

- [BrillouinZoneMeshes.jl](https://github.com/numericalEFT/BrillouinZoneMeshes.jl): Compact mesh systems for representing and manipulating functions defined on generic Brillouin zone in 2D or 3D. 

### Toolbox packages: integrated software for quantum many-body problems

- [GreenFunc.jl](https://github.com/numericalEFT/GreenFunc.jl): A software to calculate, manipulate and analyze the Green's functions and the vertex functions at the tree-level, which characterize the quantum field dynamics in the semiclassical limit ħ→0. It consists of:
  - A container of generic Green's functions based on the discrete Lehmann representation and adaptive mesh systems. 
  - Several helper functions to generate typical Green's functions. For example, a set of functions to calculate the many-body Green's functions of a small cluster of Hubbard-type atoms is a small-scale exact diagonalization solver. 
  - Import(export) Green's function from(to) the [Triqs](https://triqs.github.io/triqs/latest/).

- [MultiLoop.jl](https://github.com/numericalEFT/MultiLoop.jl) (WIP): A software to calculate and analyze the quantum many-body effects beyond the semiclassical limit. It consists of:
  - Diagrammatic Monte Carlo calculator of multi-loop Feynman diagrams of correlation functions and vertex functions. 
  - Renormalization technique to improve the perturbation theory.
  - Renormalization Group analysis.

### Applications

- [ElectronGas.jl](https://github.com/numericalEFT/ElectronGas.jl): A package that uses the numerical EFT to explore many-fermion systems with singular interactions. It can be used to study the uniform electron gas problem, Hertz-Millis theory, etc. 

- QuantumMaterials.jl (WIP): Ab-initio methods for real materials based on an effective field theory.

<!-- - Fast elementary math functions. Some of them are adapted from the package [Yeppp.jl](https://github.com/JuliaMath/Yeppp.jl). It supports more generic array types than the original package. -->


## Installation

This package has been registered. So, simply type ``import Pkg; Pkg.add("NumericalEFT")`` in the Julia REPL to install.

## Questions and Contributions

Contributions are very welcome, as are feature requests and suggestions. Please open an issue if you encounter any problems.
