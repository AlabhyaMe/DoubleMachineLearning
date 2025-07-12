# 🧠 Causal Inference in Marketing: A/B Testing vs. Double Machine Learning

This project explores the effectiveness of a bank marketing campaign aimed at increasing Certificate of Deposit (CD) subscriptions. It demonstrates a common workflow in data science — starting with a standard A/B test and progressing to a more advanced causal inference technique, **Double Machine Learning (DML)** — to ensure the robustness of the findings.

---

## 🎯 Project Overview

The core objective is to **accurately measure the causal impact** of a promotional marketing campaign on customer behavior. While a traditional A/B test provides a strong baseline, this analysis goes a step further to account for potential **confounding variables** that could influence the results.

---

## 🧪 Methodology

The analysis is conducted in two primary stages:

---

### 1️⃣ The A/B Test: A First Look at Causality

The initial analysis relies on a classic **A/B test** (randomized controlled trial). A segment of customers was randomly selected to receive a promotional offer (the _treatment_ group), while the rest were not (the _control_ group).

- **Goal**: Estimate the **Average Treatment Effect (ATE)** by comparing mean CD subscription rates between the two groups.
- **Strength**: Randomization helps ensure group comparability — it's the gold standard for causal inference.

---

### 2️⃣ The Need for Deeper Analysis: The Problem of Confounders

Even with a randomized design, we may still question the true source of observed effects:

❓ Are mobile banking users more likely to open a CD regardless of the promotion?

❓ Could **income** or **existing savings** play a bigger role than the campaign?

Such confounders can bias our results. A simple A/B test may not fully **isolate the effect** of the campaign from these underlying variables.

---

### 3️⃣ Double Machine Learning (DML): A More Robust Estimate

To address potential confounding, we employ **Double Machine Learning**.

- **Goal**: Estimate the **true causal effect** of the promotion, accounting for variables like mobile banking, income, and savings.

- **How it Works**:
  - ML models predict the outcome (`Y`) and treatment assignment (`D`) using covariates (`X`).
  - Residuals are computed:  
    \[
    Y_{\text{residual}} = Y - \hat{Y}, \quad D_{\text{residual}} = D - \hat{D}
    \]
  - We regress outcome residuals on treatment residuals to estimate the **de-biased causal effect**.

- **Why it's Powerful**:  
  By adjusting for hidden biases, DML helps ensure that the estimated treatment effect is **truly due to the campaign** — not confounding customer traits.

---

