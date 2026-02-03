# Learning Probability Density Functions using Roll-Number Parameterized Non-Linear Model

## Assignment Overview

This project learns a probability density function (PDF) from NO₂ air-quality data using a roll-number-parameterized non-linear transformation.

---

## Step 1 — Data Collection

- The NO₂ pollutant values are extracted from the dataset.
- Missing values are removed to ensure reliable statistics.
- Only valid numeric entries are used.

---

## 📂 Dataset

**India Air Quality Dataset**  
Source: Kaggle  
https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

Feature used:


---

## Step-2: Non-Linear Transformation

Each NO₂ value (x) is transformed into (z):

\[
z = x + a_r * sin(b_r * x)
\]

Where:

\[
a_r = 0.05 * (r % 7)
\]

\[
b_r = 0.3 * ((r % 5) + 1)
\]

`r` = University roll number (102316020)

### Why this step?

- Introduces controlled non-linearity
- Makes each student’s dataset unique
- Simulates feature engineering
- Helps observe distributional changes

---

## Step-3: Statistical Modeling

We assume the transformed data follows a Gaussian-like distribution:

\[
p^​(z)=c * exp(−λ * (z−μ)^2)
\]

Parameters to learn:

- μ (mean)
- λ (precision parameter)
- c (normalization constant)

This is equivalent to a normal distribution written in exponential form.

---

## Parameter Estimation

Using statistical estimation:

### Mean (μ)

Represents the center of the distribution.

\[
mu = mean(z)
\]



### Precision (λ)

Inverse spread measure.

\[
lambda_est = 1/(2*var)
\]

### Normalization Constant (c)

Ensures total probability equals 1.

\[
c_est = sqrt(lambda_est/pi)
\]

---

# Result Table

| Parameter | Meaning | Estimated Value |
|----------|--------|----------------|
| μ | Mean of z |  25.80619729 |
| λ | Precision |0.00161365 |
| c | Normalization constant | 0.02266365|
---
