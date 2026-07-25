🦠 Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data

<p align="center">"Python" (https://img.shields.io/badge/Python-3.10+-blue.svg)
"PyTorch" (https://img.shields.io/badge/PyTorch-2.x-red.svg)
"License" (https://img.shields.io/badge/License-MIT-green.svg)
"Status" (https://img.shields.io/badge/Status-Research-orange.svg)

</p><p align="center">
A <b>Physics-Informed Neural Network (PINN)</b> framework for learning hidden epidemic dynamics and estimating <b>time-varying SEIRD epidemiological parameters</b> directly from real COVID-19 data.
</p>---

📌 Overview

This repository presents a Physics-Informed Neural Network (PINN) framework for modeling infectious disease dynamics using the SEIRD (Susceptible–Exposed–Infected–Recovered–Deceased) compartmental model.

Unlike conventional numerical approaches that require predefined epidemiological parameters, the proposed framework integrates the governing SEIRD differential equations directly into the neural network training process. The model simultaneously learns hidden epidemic states and time-varying parameters from observed COVID-19 data while ensuring that the learned dynamics remain physically consistent.

---

✨ Key Features

- Physics-Informed Neural Network (PINN)
- Time-Varying SEIRD Model
- Automatic Differentiation using PyTorch
- Hidden Epidemic State Estimation
- Time-Varying Transmission, Recovery, Incubation, and Mortality Rates
- Real COVID-19 Data Analysis
- GPU Compatible
- Google Colab Ready
- Fully Reproducible Research Code

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
├── models/
│   └── pinn.py
│
├── figures/
│   ├── architecture.png
│   ├── infected_prediction.png
│   ├── recovered_prediction.png
│   ├── deaths_prediction.png
│   ├── hidden_states.png
│   └── learned_parameters.png
│
├── train.py
├── requirements.txt
├── README.md
└── LICENSE

---

🏗️ Model Architecture

Upload your architecture figure as:

figures/
└── architecture.png

Then the following code will automatically display it.

<p align="center">
<img src="figures/architecture.png" width="950">
</p><p align="center">
<b>Figure 1.</b> Architecture of the proposed Time-Varying SEIRD Physics-Informed Neural Network. The framework receives normalized time as input, predicts hidden epidemic states and time-varying epidemiological parameters, and is optimized using both observed COVID-19 data and SEIRD differential equation constraints.
</p>---

🧮 Mathematical Model

The epidemic dynamics are governed by

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

- S(t) = Susceptible Population
- E(t) = Exposed Population
- I(t) = Infected Population
- R(t) = Recovered Population
- D(t) = Deceased Population

The network also estimates

- β(t) – Transmission Rate
- σ(t) – Incubation Rate
- γ(t) – Recovery Rate
- μ(t) – Mortality Rate

---

🧠 PINN Architecture

Normalized Time
        │
        ▼
 Fully Connected Layer
        │
      Tanh
        │
 Fully Connected Layer
        │
      Tanh
        │
 Fully Connected Layer
        │
      Tanh
        │
 Fully Connected Layer
        │
        ▼
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

⚙️ Loss Function

The network is trained by minimizing

[
L=L_{Data}+L_{Physics}+L_{Initial}
]

where

- Data Loss fits observed epidemic data.
- Physics Loss enforces the SEIRD differential equations.
- Initial Condition Loss satisfies the known initial epidemic conditions.

---

📊 Dataset

The project uses the public COVID-19 dataset containing

- Confirmed Cases
- Active Cases
- Recovered Cases
- Deaths

Data preprocessing includes

- Country filtering
- Time indexing
- Missing-value handling
- Normalization using MinMaxScaler

---

🚀 Installation

Clone the repository

git clone https://github.com/yourusername/SEIRD-PINN.git

Move into the project directory

cd SEIRD-PINN

Install dependencies

pip install -r requirements.txt

---

📦 Requirements

Python >= 3.10

PyTorch

NumPy

Pandas

Matplotlib

Scikit-learn

KaggleHub

---

▶️ Running the Project

Train the model

python train.py

or open

SEIRD_PINN.ipynb

using Google Colab.

---

📈 Outputs

The trained PINN estimates

- Hidden Susceptible Population
- Hidden Exposed Population
- Active Infected Population
- Recovered Population
- Death Population
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
- Hidden SEIRD States
- Learned Transmission Rate
- Learned Incubation Rate
- Learned Recovery Rate
- Learned Mortality Rate
- Training Loss Curves

---

📁 Figures

Save all generated figures inside

figures/
│
├── architecture.png
├── infected_prediction.png
├── recovered_prediction.png
├── deaths_prediction.png
├── hidden_states.png
└── learned_parameters.png

---

🔬 Applications

This framework can be applied to

- COVID-19 Modeling
- Infectious Disease Forecasting
- Scientific Machine Learning
- Physics-Informed Deep Learning
- Public Health Analytics
- Epidemic Simulation
- Parameter Identification

---

🔮 Future Work

- Vaccination-aware SEIRDV Model
- Bayesian PINNs
- Uncertainty Quantification
- Graph Neural PINNs
- Hybrid PINN-LSTM Models
- Multi-country Epidemic Modeling
- Real-Time Forecasting

---

📚 Citation

If you use this repository in your research, please cite:

@article{SEIRDPINN2026,
  title={Learning Hidden Epidemic Dynamics Using a Time-Varying SEIRD Physics-Informed Neural Network from Real COVID-19 Data},
  author={Your Name},
  journal={Under Review},
  year={2026}
}

---

🙏 Acknowledgments

This project was developed using

- PyTorch
- Physics-Informed Neural Networks (PINNs)
- COVID-19 Open Dataset
- Scientific Machine Learning methodologies

---

📄 License

This project is distributed under the MIT License.

---

⭐ Support

If you find this repository useful, please consider:

⭐ Starring this repository

📖 Citing the associated publication

🤝 Contributing improvements through pull requests

Your support helps improve open-source scientific machine learning research.
