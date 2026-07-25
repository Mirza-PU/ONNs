🦠 Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data

A Physics-Informed Neural Network (PINN) framework for learning hidden epidemic dynamics and estimating time-varying SEIRD epidemiological parameters directly from real COVID-19 data.

---

📌 Overview

This repository presents a deep learning framework based on Physics-Informed Neural Networks (PINNs) for modeling infectious disease dynamics using the SEIRD (Susceptible–Exposed–Infected–Recovered–Deceased) compartmental model.

The proposed framework integrates epidemiological differential equations into the neural network training process, enabling simultaneous learning of hidden epidemic states and time-varying parameters from observed COVID-19 data. Unlike conventional numerical methods that require predefined parameters, the PINN automatically discovers the underlying disease dynamics while satisfying the governing physical laws.

---

✨ Features

- Physics-Informed Neural Network (PINN)
- Time-Varying SEIRD Model
- Automatic Differentiation using PyTorch
- Learning Hidden Epidemic States
- Estimation of Time-Varying Epidemiological Parameters
- COVID-19 Data Analysis
- GPU Compatible
- Google Colab Ready
- End-to-End Deep Learning Framework

---

📂 Repository Structure

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

🏗 Model Architecture

«Upload your architecture diagram as "figures/architecture.png".»

<p align="center">
  <img src="figures/architecture.png" width="900">
</p><p align="center">
<b>Figure 1.</b> Architecture of the proposed Time-Varying SEIRD Physics-Informed Neural Network. The framework receives normalized time as input, predicts hidden SEIRD states and time-varying epidemiological parameters, and optimizes the network using observed COVID-19 data together with the governing SEIRD differential equations.
</p>---

🧮 Mathematical Model

The epidemic dynamics are governed by the following SEIRD differential equations:

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

- S(t) = Susceptible population
- E(t) = Exposed population
- I(t) = Infected population
- R(t) = Recovered population
- D(t) = Deceased population

The model simultaneously estimates

- β(t) — Transmission Rate
- σ(t) — Incubation Rate
- γ(t) — Recovery Rate
- μ(t) — Mortality Rate

---

🧠 Physics-Informed Neural Network

The neural network receives normalized time as input

Input
 │
 ▼
Normalized Time t
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Output Layer
 │
 ▼
S(t), E(t), I(t), R(t), D(t),
β(t), σ(t), γ(t), μ(t)

---

⚙ Loss Function

The total optimization objective consists of three components:

[
L=L_{Data}+L_{Physics}+L_{Initial}
]

where

- Data Loss minimizes the difference between observed and predicted epidemic data.
- Physics Loss enforces the SEIRD differential equations.
- Initial Condition Loss satisfies the known initial epidemic conditions.

---

📊 Dataset

This project uses the publicly available COVID-19 dataset containing

- Confirmed Cases
- Active Cases
- Recovered Cases
- Deaths

The data are normalized before model training.

---

🚀 Installation

Clone the repository

git clone https://github.com/yourusername/SEIRD-PINN.git

Move into the project directory

cd SEIRD-PINN

Install the required packages

pip install -r requirements.txt

---

📦 Requirements

Python >= 3.10

PyTorch

NumPy

Pandas

Matplotlib

scikit-learn

kagglehub

---

▶ Running the Project

Run the training script

python train.py

or simply open

SEIRD_PINN.ipynb

using Google Colab.

---

📈 Model Outputs

The trained PINN predicts

- Hidden Susceptible Population
- Hidden Exposed Population
- Active Infected Population
- Recovered Population
- Deceased Population
- Transmission Rate β(t)
- Incubation Rate σ(t)
- Recovery Rate γ(t)
- Mortality Rate μ(t)

---

📉 Visualization

The repository generates

- Real vs Predicted Infected Cases
- Real vs Predicted Recovered Cases
- Real vs Predicted Death Cases
- Hidden Epidemic States
- Learned Transmission Rate
- Learned Incubation Rate
- Learned Recovery Rate
- Learned Mortality Rate
- Training Loss Curves

---

📁 Figures

Store all generated figures inside

figures/

architecture.png

infected_prediction.png

recovered_prediction.png

deaths_prediction.png

hidden_states.png

learned_parameters.png

---

🔬 Applications

The proposed framework can be applied to

- COVID-19 epidemic modeling
- Influenza prediction
- Emerging infectious diseases
- Public health decision support
- Physics-informed machine learning
- Scientific machine learning
- Epidemic forecasting

---

🔮 Future Work

- Vaccination-aware SEIRDV model
- Bayesian Physics-Informed Neural Networks
- Uncertainty Quantification
- Multi-country epidemic prediction
- Graph Neural PINNs
- Hybrid PINN-LSTM framework
- Real-time epidemic forecasting

---

📚 Citation

If you use this repository in your research, please cite

@article{SEIRD_PINN_2026,
  title={Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data},
  author={Author(s)},
  journal={Under Review},
  year={2026}
}

---

🙏 Acknowledgments

This work was developed using

- PyTorch
- Physics-Informed Neural Networks (PINNs)
- COVID-19 Open Dataset
- Scientific Machine Learning techniques

---

📄 License

This project is distributed under the MIT License.

---

⭐ Support

If you find this repository useful for your research, please consider starring ⭐ the repository and citing the associated publication.🦠 Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data

A Physics-Informed Neural Network (PINN) framework for learning hidden epidemic dynamics and estimating time-varying SEIRD epidemiological parameters directly from real COVID-19 data.

---

📌 Overview

This repository presents a deep learning framework based on Physics-Informed Neural Networks (PINNs) for modeling infectious disease dynamics using the SEIRD (Susceptible–Exposed–Infected–Recovered–Deceased) compartmental model.

The proposed framework integrates epidemiological differential equations into the neural network training process, enabling simultaneous learning of hidden epidemic states and time-varying parameters from observed COVID-19 data. Unlike conventional numerical methods that require predefined parameters, the PINN automatically discovers the underlying disease dynamics while satisfying the governing physical laws.

---

✨ Features

- Physics-Informed Neural Network (PINN)
- Time-Varying SEIRD Model
- Automatic Differentiation using PyTorch
- Learning Hidden Epidemic States
- Estimation of Time-Varying Epidemiological Parameters
- COVID-19 Data Analysis
- GPU Compatible
- Google Colab Ready
- End-to-End Deep Learning Framework

---

📂 Repository Structure

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

🏗 Model Architecture

«Upload your architecture diagram as "figures/architecture.png".»

<p align="center">
  <img src="figures/architecture.png" width="900">
</p><p align="center">
<b>Figure 1.</b> Architecture of the proposed Time-Varying SEIRD Physics-Informed Neural Network. The framework receives normalized time as input, predicts hidden SEIRD states and time-varying epidemiological parameters, and optimizes the network using observed COVID-19 data together with the governing SEIRD differential equations.
</p>---

🧮 Mathematical Model

The epidemic dynamics are governed by the following SEIRD differential equations:

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

- S(t) = Susceptible population
- E(t) = Exposed population
- I(t) = Infected population
- R(t) = Recovered population
- D(t) = Deceased population

The model simultaneously estimates

- β(t) — Transmission Rate
- σ(t) — Incubation Rate
- γ(t) — Recovery Rate
- μ(t) — Mortality Rate

---

🧠 Physics-Informed Neural Network

The neural network receives normalized time as input

Input
 │
 ▼
Normalized Time t
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Fully Connected Layer
 │
 ▼
Tanh Activation
 │
 ▼
Output Layer
 │
 ▼
S(t), E(t), I(t), R(t), D(t),
β(t), σ(t), γ(t), μ(t)

---

⚙ Loss Function

The total optimization objective consists of three components:

[
L=L_{Data}+L_{Physics}+L_{Initial}
]

where

- Data Loss minimizes the difference between observed and predicted epidemic data.
- Physics Loss enforces the SEIRD differential equations.
- Initial Condition Loss satisfies the known initial epidemic conditions.

---

📊 Dataset

This project uses the publicly available COVID-19 dataset containing

- Confirmed Cases
- Active Cases
- Recovered Cases
- Deaths

The data are normalized before model training.

---

🚀 Installation

Clone the repository

git clone https://github.com/yourusername/SEIRD-PINN.git

Move into the project directory

cd SEIRD-PINN

Install the required packages

pip install -r requirements.txt

---

📦 Requirements

Python >= 3.10

PyTorch

NumPy

Pandas

Matplotlib

scikit-learn

kagglehub

---

▶ Running the Project

Run the training script

python train.py

or simply open

SEIRD_PINN.ipynb

using Google Colab.

---

📈 Model Outputs

The trained PINN predicts

- Hidden Susceptible Population
- Hidden Exposed Population
- Active Infected Population
- Recovered Population
- Deceased Population
- Transmission Rate β(t)
- Incubation Rate σ(t)
- Recovery Rate γ(t)
- Mortality Rate μ(t)

---

📉 Visualization

The repository generates

- Real vs Predicted Infected Cases
- Real vs Predicted Recovered Cases
- Real vs Predicted Death Cases
- Hidden Epidemic States
- Learned Transmission Rate
- Learned Incubation Rate
- Learned Recovery Rate
- Learned Mortality Rate
- Training Loss Curves

---

📁 Figures

Store all generated figures inside

figures/

architecture.png

infected_prediction.png

recovered_prediction.png

deaths_prediction.png

hidden_states.png

learned_parameters.png

---

🔬 Applications

The proposed framework can be applied to

- COVID-19 epidemic modeling
- Influenza prediction
- Emerging infectious diseases
- Public health decision support
- Physics-informed machine learning
- Scientific machine learning
- Epidemic forecasting

---

🔮 Future Work

- Vaccination-aware SEIRDV model
- Bayesian Physics-Informed Neural Networks
- Uncertainty Quantification
- Multi-country epidemic prediction
- Graph Neural PINNs
- Hybrid PINN-LSTM framework
- Real-time epidemic forecasting

---

📚 Citation

If you use this repository in your research, please cite

@article{SEIRD_PINN_2026,
  title={Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data},
  author={Author(s)},
  journal={Under Review},
  year={2026}
}

---

🙏 Acknowledgments

This work was developed using

- PyTorch
- Physics-Informed Neural Networks (PINNs)
- COVID-19 Open Dataset
- Scientific Machine Learning techniques

---

📄 License

This project is distributed under the MIT License.

---

⭐ Support

If you find this repository useful for your research, please consider starring ⭐ the repository and citing the associated publication.
