# 🛌 Sleep Quality Analysis

## 📘 Introduction

This project explores the relationships between various lifestyle and physiological factors and **sleep quality**. The goal is to identify which variables significantly affect sleep quality and how sleep, in turn, impacts mood and productivity. The analysis is hypothesis-driven and uses Ordinary Least Squares (OLS) regression models, including models with interaction terms, to test these relationships.

---

## 📊 Data Description

- **Sources**:
  - [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset)
  - [Sleep Cycle and Productivity Dataset](https://www.kaggle.com/datasets/adilshamim8/sleep-cycle-and-productivity)
- **Variables**: Includes `Stress Level`, `BMI Category`, `Resting Heart Rate`, `Daily Steps`, `Age`, `Exercise`, `Screen Time`, `Caffeine Intake`, `Mood Score`, `Productivity Score`, and `Sleep Quality`.
- **Challenges**:
  - Missing values
  - Potential multicollinearity
  - Subjective measures (e.g., mood, productivity)
- **Strengths**:
  - Rich, multi-variable data
  - Time-based metrics for behavior and physiology
  - Multiple measures of well-being and lifestyle

---

## ❓ Research Questions & Hypotheses

### 💤 Effects on Sleep Quality

**Q1: Does stress level influence sleep quality?**  
- H₀: No relationship  
- H₁: Higher stress levels negatively impact sleep quality  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.067 (> 0.05)

**Q2: Does BMI category affect sleep quality?**  
- H₀: No effect  
- H₁: Normal BMI correlates with better sleep  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.854 (> 0.05)

**Q3: Is resting heart rate related to sleep quality?**  
- H₀: No relationship  
- H₁: Lower resting HR predicts better sleep  
**✔️ Conclusion**: H₀ is **rejected** — p-value = 0.000 (< 0.005); higher heart rate = lower sleep quality

**Q4: Do daily steps predict better sleep quality?**  
- H₀: No effect  
- H₁: More steps → better sleep  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.992 (> 0.05)

### 🔄 Combined Effects on Sleep Quality

**Q5: Interaction between age and exercise on sleep quality**  
- H₀: No interaction  
- H₁: Older people benefit more from exercise in terms of sleep quality  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.236 (> 0.05)

**Q6: Combined screen time and caffeine intake effect**  
- H₀: No joint influence  
- H₁: High values of both harm sleep quality  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.844 (> 0.05)

### 🌤 Effects of Sleep Quality

**Q7: Does sleep quality affect mood?**  
- H₀: No effect  
- H₁: Better sleep → better mood  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.676 (> 0.05)

**Q8: Does sleep quality affect productivity?**  
- H₀: No effect  
- H₁: Better sleep → higher productivity  
**✔️ Conclusion**: H₀ is **not rejected** — p-value = 0.934 (> 0.05)

---

## 🔬 Methodology

1. **Data Cleaning**
   - Removed missing and implausible values
   - Handled outliers
   - Encoded categorical variables
2. **Exploratory Data Analysis**
   - Correlation matrices and pairplots
   - Distribution plots to understand scale and skewness
3. **Modeling**
   - Ordinary Least Squares (OLS) regression
   - Included interaction terms for combined effects
   - Checked regression assumptions: normality, homoscedasticity, multicollinearity
4. **Evaluation**
   - Interpreted R², p-values, and regression coefficients
   - Visualized regression fits with seaborn `regplot`

---

## 📈 Conclusions

### Overall Model Fit

- The model to predict **Sleep Quality** explains only **0.07%** of the variance (`R² = 0.0007`), indicating very low predictive power.
- Nevertheless, **p-values** help determine statistical significance of individual variables.

### Effects on Sleep Quality

- **Resting Heart Rate** has a significant negative effect: individuals with lower HR tend to sleep better.
- **Stress Level**, **BMI**, and **Daily Steps** show **no statistically significant relationship** with sleep quality.

### Combined Effects

- Models with interaction terms (**Age × Exercise**, **Screen Time × Caffeine**) explain virtually none of the variance in sleep quality (`R² = 0.001` and `R² = 0.000`).
- Neither interaction shows statistical significance.

### Effects of Sleep Quality on Other Outcomes

- Models predicting **Mood Score** and **Productivity Score** from sleep quality both have `R² = 0.000`, showing no explanatory power.
- No significant relationships found in either case (p > 0.05).

---

## 🔍 Further Questions

- Could time-series modeling uncover lagged effects (e.g., cumulative screen time over days)?
- Would a machine learning model (e.g., Random Forest) find nonlinear patterns missed by OLS?
- How do sleep **duration** and **sleep stages** affect the outcome differently?

---

## 🔗 Resources

- [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset)
- [Sleep Cycle and Productivity Dataset](https://www.kaggle.com/datasets/adilshamim8/sleep-cycle-and-productivity)
- Trello/Kanban Board: _(Insert your Trello link here)_
