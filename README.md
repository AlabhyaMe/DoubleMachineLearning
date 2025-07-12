Causal Inference in Marketing: A/B Testing vs. Double Machine Learning
This project explores the effectiveness of a bank marketing campaign aimed at increasing Certificate of Deposit (CD) subscriptions. It demonstrates a common workflow in data science, starting with a standard A/B test and progressing to a more advanced causal inference technique, Double Machine Learning (DML), to ensure the robustness of the findings.

Project Overview
The core objective is to accurately measure the causal impact of a promotional marketing campaign on customer behavior. While a traditional A/B test provides a strong baseline, this analysis goes a step further to account for potential confounding variables that could influence the results.

Methodology
The analysis is conducted in two primary stages:

1. The A/B Test: A First Look at Causality
The initial analysis relies on a classic A/B test (randomized controlled trial). A segment of customers was randomly selected to receive a promotional offer (the "treatment" group), while the rest were not (the "control" group).

Goal: To get a direct estimate of the Average Treatment Effect (ATE) by comparing the mean outcomes (CD subscriptions) between the two groups.

Strength: Randomization is the gold standard for causal inference, as it helps to ensure, on average, that the two groups are comparable before the intervention.

2. The Need for Deeper Analysis: The Problem of Confounders
Even with a well-designed experiment, questions can arise about the underlying drivers of the observed effect. Certain customer characteristics might be correlated with both the outcome and, subtly, with the treatment.

For example:

Are customers who use the mobile banking app naturally more likely to open a CD, regardless of the promotion?

Do factors like income or existing savings levels play a more significant role than the campaign itself?

These confounding variables can make it difficult to isolate the true impact of the marketing campaign. A simple A/B test might not fully disentangle these effects, leading to a potentially misleading interpretation of why the campaign succeeded.

3. Double Machine Learning (DML): A More Robust Estimate
To address the potential influence of confounders, we employ Double Machine Learning (DML).

Goal: To get a more robust estimate of the treatment effect by explicitly modeling and removing the influence of confounding variables (e.g., mobile banking usage, savings, income, etc.).

How it Works: DML uses machine learning to predict the outcome based on the confounders and to predict the treatment assignment based on the confounders. By analyzing the relationship between the parts that cannot be predicted (the residuals), DML isolates the pure, causal effect of the treatment.

Why it's Powerful: This method provides a "de-biased" estimate of the campaign's impact, giving us greater confidence that the effect we measure is due to the promotion itself and not just the characteristics of the customers who received it.

How to Use This Repository
Clone the repository:

git clone [your-repository-url]

Install dependencies:

pip install -r requirements.txt

Run the analysis:

The project is structured in notebooks or scripts, starting with the initial A/B test analysis and followed by the DML implementation.

01_AB_Test_Analysis.ipynb

02_DoubleML_Causal_Inference.ipynb
