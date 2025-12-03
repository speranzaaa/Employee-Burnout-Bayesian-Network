# Causal Analysis of Employee Burnout
### A Bayesian Network Approach to Workplace Well-being

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-pgmpy-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project models the causal drivers of employee burnout using **Discrete Bayesian Networks (BNs)**. By moving beyond simple correlation, we aim to understand the conditional dependencies between job characteristics (e.g., Salary, Remote Work), demographics, and mental health outcomes.

The project implements structural learning algorithms constrained by **Expert Knowledge** to build a Directed Acyclic Graph (DAG) that represents the causal mechanisms of burnout.

## 💡 Key Findings
Using Causal Inference and Sensitivity Analysis, we discovered that:
* **Lifestyle over Money:** `Physical Activity` and `Work-Life Balance` are significantly stronger predictors of burnout than `Salary Range`.
* **The "Active" Intervention:** Simulating an intervention showed that shifting from a sedentary to an active lifestyle reduces burnout risk by over **10%**, whereas a salary raise yields a negligible reduction (< 1%).
* **Stress as a Hub:** Stress acts as the primary mediator between job demands and burnout risk.

## 📊 Dataset
The analysis is based on the **Mental Health and Burnout in the Workplace** dataset.
* **Original Source:** [Kaggle - Mental Health and Burnout in the Workplace](https://www.kaggle.com/datasets/khushikyad001/mental-health-and-burnout-in-the-workplace/data)

*Note: The raw data was preprocessed (discretized) to be suitable for Discrete Bayesian Network learning.*

## 🛠️ Methodology & Tech Stack
The analysis is performed in a **Jupyter Notebook** using the `pgmpy` library.

### 1. Structure Learning
We compared two approaches to learn the network structure:
* **Score-Based:** `HillClimbSearch` utilizing the **AIC (Akaike Information Criterion)** score.
* **Constraint-Based:** `PC (Peter-Clark) Algorithm` utilizing Chi-square independence tests.

*Note: We injected **Expert Knowledge** (blacklisting edges) to prevent logical fallacies (e.g., Mental State $\to$ Demographics).*

### 2. Parameter Learning
* Conditional Probability Tables (CPTs) were learned using **Bayesian Estimation** to handle data sparsity.

### 3. Inference
* We used **Variable Elimination** for exact inference to run "What-If" scenarios.

## 🚀 How to Run
1. Clone the repo:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/employee-burnout-bayesian-network.git](https://github.com/YOUR_USERNAME/employee-burnout-bayesian-network.git)
