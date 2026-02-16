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
![Original Data](path/to/original_data.png)

### Transformation Function
![Transformation](path/to/transformation_function.png)

### Transformed Data Distribution
![Transformed Data](path/to/transformed_data.png)

### Fitted PDF vs Empirical Distribution
![Fitted PDF](path/to/fitted_pdf.png)

### Residual Analysis
![Residuals](path/to/residuals.png)

### Q-Q Plot
![Q-Q Plot](path/to/qq_plot.png)

### CDF Comparison
![CDF](path/to/cdf_comparison.png)

### Summary Panel
![Summary](path/to/summary_panel.png)

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
