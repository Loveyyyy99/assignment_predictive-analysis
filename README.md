# Assignment-1: Probability Density Function Learning

## Objective
To transform air quality data using a roll-number-parameterized non-linear function and estimate parameters of a probability density function using Maximum Likelihood Estimation.

---

## Roll Number
**102303335**

---

## Dataset
- **data.csv** (India Air Quality Data)
- Feature: NO2 concentration (µg/m³)
- Samples: 29,531
- Range: [0.31, 994.00] µg/m³

---

## Methodology

1. Loaded NO2 air quality data from CSV
2. Calculated transformation parameters from roll number
3. Applied non-linear transformation: **z = x + a_r × sin(b_r × x)**
4. Estimated PDF parameters using Maximum Likelihood Estimation
5. Validated model with statistical tests and visualizations

---

## Transformation Parameters

| Parameter | Formula | Value |
|-----------|---------|-------|
| **a_r** | 0.05 × (r mod 7) | 0.050000 |
| **b_r** | 0.3 × ((r mod 5) + 1) | 0.300000 |

**Transformation Function:**
```
z = x + 0.050000 × sin(0.300000 × x)
```

---

## Results

### Fitted PDF Parameters
**Model:** p̂(z) = c × e^(-λ(z-μ)²)

| Parameter | Value |
|-----------|-------|
| **λ (lambda)** | 0.002058 |
| **μ (mu)** | 19.63 |
| **c** | 0.0268 |

---

### Model Quality Metrics

| Metric | Value | Status |
|--------|-------|--------|
| R² Score | 0.9847 | ✓ Excellent |
| Mean Squared Error | 0.00000263 | ✓ Very Low |
| PDF Integration | 0.9446 | ✓ Near 1.0 |
| KS Statistic | 0.0962 | ✓ Good Fit |
| Residual Mean | 0.000055 | ✓ Centered |
| Residual Std | 0.000263 | ✓ Small Variance |

---

## Visualizations

### Original Data Distribution
<img width="701" height="494" alt="image" src="https://github.com/user-attachments/assets/f921b7f0-29c8-45f6-8aec-0e32b7ab35bb" />

### Transformation Function
<img width="1389" height="489" alt="transformation effect" src="https://github.com/user-attachments/assets/1234a387-3b45-4972-bdb6-97fc0c1bce43" />

### Transformed Data Distribution
<img width="1390" height="490" alt="transformed data distribution" src="https://github.com/user-attachments/assets/ca89a4a1-3c0e-438f-81d2-06191d50a75e" />

### Fitted PDF vs Empirical Distribution
<img width="1390" height="590" alt="empiricaldistribution" src="https://github.com/user-attachments/assets/9bca2657-dfbe-44e9-8716-0516badd42f4" />

### Residual Analysis
<img width="1389" height="490" alt="distribution" src="https://github.com/user-attachments/assets/885cc226-c7b8-45be-bf59-a777a87fbdd7" />

### Q-Q Plot
<img width="989" height="590" alt="quantile" src="https://github.com/user-attachments/assets/3b6c8c94-8929-4d7a-b5b2-d2f142c62cca" />

### CDF Comparison
<img width="1189" height="590" alt="cdf" src="https://github.com/user-attachments/assets/4056dcee-4204-4f6b-b7a8-f33d02862da4" />

### Summary Panel
<img width="1589" height="989" alt="output" src="https://github.com/user-attachments/assets/6f5e4841-6ba8-4538-a59c-39baeb5434d2" />

---

## Conclusion

- Transformation successfully applied with roll-number-specific parameters
- MLE converged with high accuracy (R² = 0.9847)
- Residuals are well-centered with minimal variance
- PDF integration validates proper normalization
- Model captures the transformed data distribution effectively

---

## How to Run

1. **Install dependencies:**
```bash
   pip install numpy pandas matplotlib scipy
```

2. **Run the notebook:**
```bash
   jupyter notebook assignment.ipynb
```

3. **Update Cell 2:**
   - Set `ROLL_NUMBER = 102303335`

4. **Execute all cells sequentially**

---

## Project Structure
```
├── data.csv                    # Input air quality dataset
├── assignment.ipynb            # Main analysis notebook (19 cells)
└── README.md                   # This file
```

---

## Submission

**Link:** https://forms.gle/iYF3MDKozRnSCHvR8

**Parameters to Submit:**
```
λ (lambda) = 0.002058
μ (mu)     = 19.630000
c          = 0.026800
```

---
