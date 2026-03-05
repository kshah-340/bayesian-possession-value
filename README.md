# Bayesian Possession Value Model — Soccer Analytics

A Bayesian logistic regression framework for estimating the value of individual actions based on possession results, using event-level data from the StatsBomb open data repository.

Full writeup: [Medium Article](https://medium.com/@kiran_30122/a-bayesian-approach-to-quantifying-soccer-possession-value-a7d17435bf35)

---

## Overview

Traditional metrics like xG evaluate individual actions in isolation. This framework evaluates entire possessions — capturing the buildup, not just the finish. The model assigns value to actions based on their type, location, and timing within a possession sequence.

Three prior specifications are tested to assess sensitivity to prior assumptions:
- Semi-informative baseline: Normal(0, 1.5)
- Uninformative: Normal(0, 10)
- Regularizing: Normal(0, 0.5)

Results held up consistently across all three specifications, strengthening confidence in the key findings.

---

## Key Findings

- The baseline goal probability recovered by the model (~0.9%) matches the empirical rate in professional soccer without explicit calibration
- Shot is the strongest predictor of possession success, but timing matters — the value of entering the attacking third scales up significantly the later in a possession it occurs
- Uninformative priors produced implausibly extreme estimates for sparse features like cutbacks, illustrating the importance of prior choice in low-signal sports data
- Uncertainty estimates are as informative as point estimates in a sport decided by margins this thin

---

## Repository Structure
```
bayesian-possession-value/
│
├── notebooks/
│   └── possession_model.ipynb    # Full analysis walkthrough
│
├── figures/
│   ├── coefficient_plot.png
│   ├── prior_comparison.png
│   └── pitch_diagram.png
│
├── data/
│   └── README.md                 # Data sourcing instructions
│
├── requirements.txt
└── README.md
```

---

## Data

This project uses StatsBomb open data, which is freely available for non-commercial use. See [`data/README.md`](data/README.md) for setup instructions.

---

## Requirements

See `requirements.txt`. To install:
```bash
pip install -r requirements.txt
```

---

## Author

Kiran Shah
MS Analytics, Georgia Tech | Former DC United Analytics
[LinkedIn](https://www.linkedin.com/in/kiran-shah-340ax/) | [Medium](https://medium.com/@kiran_30122/a-bayesian-approach-to-quantifying-soccer-possession-value-a7d17435bf35)
```

---

## 2. Main Code File

You have two options here — I'd recommend doing both:

**Option A: Jupyter Notebook**

This is the more readable format for someone evaluating your work. If your code is already in a `.ipynb` file, upload it directly. If it's in a `.py` script, you'll want to convert it.

To upload: Go to your repo → **Add file → Upload files** → drag and drop your `.ipynb` file into the `notebooks/` folder (type `notebooks/` as a prefix in the file path field).

Structure your notebook so it reads top to bottom like a story:
- Cell 1: Markdown header and project description
- Cell 2: Imports
- Cell 3: Data loading with a markdown cell above explaining what the data is
- Cell 4 onward: Each major step (feature engineering, model definition, sampling, results) preceded by a markdown cell explaining what you're doing and why

**Option B: Python script**

If you also want a clean `.py` version, create a new file at `src/possession_model.py`. No redactions needed — just make sure the code is clean, commented, and readable.

---

## 3. Requirements File

Click **Add file → Create new file**, name it `requirements.txt`, and paste the following — adjusting version numbers if you know your exact ones:
```
pymc>=5.0.0
arviz>=0.15.0
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
scikit-learn>=1.2.0
statsbombpy>=1.0.0
jupyter>=1.0.0
