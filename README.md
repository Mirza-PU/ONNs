Implementation of Oscillatory Neural Networks for the Simulation of Nonlinear Dynamical Systems

Overview

This repository presents an implementation of Oscillatory Neural Networks (ONNs) for solving nonlinear dynamical systems using Physics-Informed Neural Networks (PINNs). The framework is developed with PyTorch and NeuroDiffEq and is demonstrated on the classical COVID-19 SEIR (Susceptible–Exposed–Infected–Recovered) epidemic model.

Instead of relying on conventional numerical solvers, the neural network directly learns the solution of the governing differential equations while satisfying the initial conditions. The approach provides a mesh-free, data-driven alternative for solving nonlinear ordinary differential equations.

---

Features

- Physics-informed neural network implementation
- Oscillatory neural network architecture using sinusoidal activation functions
- Automatic differentiation for differential equation constraints
- COVID-19 SEIR epidemic model simulation
- Comparison with numerical solutions
- Visualization of epidemic dynamics
- PyTorch-based implementation
- NeuroDiffEq solver integration

---

Repository Structure

.
├── data/
├── notebooks/
├── models/
├── figures/
├── results/
├── train.py
├── evaluate.py
├── requirements.txt
├── README.md
└── LICENSE

---

Model Architecture

                    Time (t)
                       │
                       ▼
                Input Layer (1)
                       │
                       ▼
          ┌──────────────────────┐
          │ Fully Connected Layer │
          │      32 Neurons       │
          └──────────────────────┘
                       │
                 Sin Activation
                       │
                       ▼
          ┌──────────────────────┐
          │ Fully Connected Layer │
          │      32 Neurons       │
          └──────────────────────┘
                       │
                 Sin Activation
                       │
                       ▼
               Output Layer (4)
          ┌──────┬──────┬──────┬──────┐
          │  S   │  E   │  I   │  R   │
          └──────┴──────┴──────┴──────┘
                       │
                       ▼
         Physics-Informed Loss Function
                       │
      Differential Equation Residuals
                       │
                       ▼
          Stochastic Gradient Descent
                       │
                       ▼
             Learned SEIR Dynamics

---

Workflow

        Initial Conditions
               │
               ▼
         Time Sampling
               │
               ▼
     Oscillatory Neural Network
               │
               ▼
   Automatic Differentiation
               │
               ▼
   SEIR Differential Equations
               │
               ▼
      Physics Loss + IC Loss
               │
               ▼
             SGD Optimizer
               │
               ▼
      Trained Neural Network
               │
               ▼
        SEIR Predictions

---

Mathematical Model

The SEIR model is defined as

[
\frac{dS}{dt}=-\frac{\beta SI}{N}
]

[
\frac{dE}{dt}=\frac{\beta SI}{N}-\epsilon E
]

[
\frac{dI}{dt}=\epsilon E-\gamma I
]

[
\frac{dR}{dt}=\gamma I
]

where

- S : Susceptible population
- E : Exposed population
- I : Infectious population
- R : Recovered population

---

Installation

git clone https://github.com/yourusername/ONNs-SEIR.git

cd ONNs-SEIR

pip install -r requirements.txt

---

Required Packages

torch
numpy
matplotlib
scipy
neurodiffeq

---

Training

python train.py

---

Output

The implementation generates

- Susceptible curve
- Exposed curve
- Infected curve
- Recovered curve
- Training convergence
- Learned neural network solution
- Comparison with numerical solution

---

Example Results

Population
│
│                 S(t)
│               ╱
│             ╱
│           ╱
│         ╱
│       ╱
│     ╱            R(t)
│   ╱            ╱
│ ╱          ╱
│╱     I(t)
└──────────────────────────► Time

---

Citation

If you use this repository, please cite the associated paper.

Implementation of Oscillatory Neural Networks
for the Simulation of Nonlinear Dynamical Systems.

---

License

This project is released under the MIT License.

---

Acknowledgments

- PyTorch
- NeuroDiffEq
- Scientific Machine Learning Community
- Mathematical Epidemiology Research Community
