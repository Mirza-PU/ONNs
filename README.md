🦠 Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network

A Physics-Informed Neural Network (PINN) framework for learning hidden epidemic dynamics and estimating time-varying SEIRD parameters directly from real COVID-19 data.

---

📖 Overview

This repository presents a deep learning framework based on Physics-Informed Neural Networks (PINNs) for modeling the spread of infectious diseases using the SEIRD (Susceptible–Exposed–Infected–Recovered–Deceased) compartmental model.

Unlike traditional numerical solvers that require explicit parameter estimation before simulation, the proposed PINN integrates the governing differential equations into the learning process. This enables simultaneous estimation of hidden epidemic states and time-varying epidemiological parameters directly from observed COVID-19 data.

The framework combines observed epidemic data with physical laws represented by the SEIRD system of ordinary differential equations (ODEs), producing accurate and physically consistent epidemic trajectories.

---

Repository Structure

SEIRD-PINN/
│
├── data/
│   ├── full_grouped.csv
│   └── processed_data.csv
│
├── notebooks/
│   └── SEIRD_PINN.ipynb
│
├── figures/
│   ├── architecture.png
│   ├── infected_prediction.png
│   ├── recovered_prediction.png
│   ├── deaths_prediction.png
│   ├── hidden_states.png
│   └── learned_parameters.png
│
├── models/
│   └── pinn.py
│
├── train.py
├── requirements.txt
├── LICENSE
└── README.md

---

Architecture

«Insert your architecture diagram here»

                COVID-19 Data
                      │
                      ▼
             Data Preprocessing
                      │
                      ▼
               Time Normalization
                      │
                      ▼
          Physics-Informed Neural Network
        (Fully Connected Neural Network)
                      │
      ┌───────────────┼────────────────┐
      ▼               ▼                ▼
 Hidden SEIRD      Time-Varying     Physics Loss
    States          Parameters         (ODEs)
      │               │
      └───────────────┼────────────────┘
                      ▼
             Total Training Loss
                      │
                      ▼
              Optimized PINN Model
                      │
                      ▼
      Predicted Epidemic Dynamics

Replace the placeholder above with your architecture figure ("figures/architecture.png") after uploading it.

---

Features

- Physics-Informed Neural Network (PINN)
- Time-varying SEIRD model
- Automatic differentiation
- Hidden state estimation
- Time-varying transmission rate
- Time-varying recovery rate
- Time-varying mortality rate
- Real COVID-19 dataset
- PyTorch implementation
- GPU compatible
- Google Colab compatible

---

Mathematical Model

The epidemic dynamics are governed by the SEIRD equations:

[
\frac{dS}{dt}=-\beta(t)\frac{SI}{N}
]

[
\frac{dE}{dt}=\beta(t)\frac{SI}{N}-\sigma(t)E
]

[
\frac{dI}{dt}=\sigma(t)E-\gamma(t)I-\mu(t)I
]

[
\frac{dR}{dt}=\gamma(t)I
]

[
\frac{dD}{dt}=\mu(t)I
]

where

- S = Susceptible population
- E = Exposed population
- I = Infected population
- R = Recovered population
- D = Deceased population

The model also estimates

- β(t): Transmission rate
- σ(t): Incubation rate
- γ(t): Recovery rate
- μ(t): Mortality rate

---

PINN Architecture

Input

Time (t)

↓

Hidden Layers

Linear
↓

Tanh

↓

Linear

↓

Tanh

↓

Linear

↓

Tanh

↓

Linear

↓

Outputs

S(t)
E(t)
I(t)
R(t)
D(t)

β(t)
σ(t)
γ(t)
μ(t)

---

Physics-Informed Loss

The total loss combines three objectives:

- Data Loss
- Physics Loss
- Initial Condition Loss

[
L=L_{data}+L_{physics}+L_{IC}
]

where

- Data Loss matches observations.
- Physics Loss enforces the SEIRD differential equations.
- Initial Condition Loss satisfies the epidemic initial conditions.

---

Dataset

The model uses the publicly available COVID-19 dataset containing:

- Confirmed cases
- Active cases
- Recovered cases
- Deaths

The data are normalized before training.

---

Installation

Clone the repository

git clone https://github.com/yourusername/SEIRD-PINN.git

cd SEIRD-PINN

Install dependencies

pip install -r requirements.txt

---

Requirements

Python 3.10+

PyTorch

NumPy

Pandas

Matplotlib

scikit-learn

kagglehub

---

Training

Run

python train.py

or open

SEIRD_PINN.ipynb

inside Google Colab.

---

Outputs

The trained model predicts

- Hidden Susceptible population
- Hidden Exposed population
- Infected population
- Recovered population
- Deaths
- Time-varying β(t)
- Time-varying σ(t)
- Time-varying γ(t)
- Time-varying μ(t)

---

Results

The repository produces:

- Real vs Predicted Infected Curve
- Real vs Predicted Recovered Curve
- Real vs Predicted Death Curve
- Hidden SEIRD States
- Learned Transmission Rate
- Learned Recovery Rate
- Learned Mortality Rate
- Training Loss Curve

---

Example Figures

figures/

├── architecture.png
├── infected_prediction.png
├── recovered_prediction.png
├── deaths_prediction.png
├── hidden_states.png
└── learned_parameters.png

---

Future Work

- SEIQRD model
- Vaccination compartment
- Multi-country epidemic modeling
- Bayesian PINNs
- Uncertainty quantification
- Forecasting future outbreaks
- Hybrid Graph Neural PINNs

---

Citation

If you use this repository in your research, please cite:

@article{yourpaper2026,
  title={Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data},
  author={Author(s)},
  journal={Under Review},
  year={2026}
}

---

Acknowledgments

This project makes use of:

- PyTorch
- Physics-Informed Neural Networks (PINNs)
- Kaggle COVID-19 Dataset
- Scientific machine learning techniques for epidemic modeling

---

License

This project is released under the MIT License.

---

⭐ If you find this project useful, please consider giving it a star on GitHub!
