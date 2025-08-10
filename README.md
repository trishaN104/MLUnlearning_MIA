# Machine Unlearning Verification with Membership Inference Attacks

## Overview
This project explores **verifying machine unlearning** using **Membership Inference Attacks (MIAs)**.  
When a model “forgets” certain data (due to legal or ethical requirements like GDPR), we check if it truly becomes indistinguishable from never having seen that data.  

MIAs attempt to guess whether a sample was part of the training data.  
If unlearning is successful, attack accuracy should drop close to **random guessing (50%)**.

---

## Methodology
### 1. Dataset  
- **Loan Approval Classification Dataset** (Kaggle)  
- Target variable: Loan approval status  
- 19 numeric + categorical features  

### 2. Forget Set  
Select high-risk loans using percentile thresholds over:
- Loan interest rate  
- Percent income  
- Loan amount  

Varying amount of forget percentiles are later tested.

### 3. Models  
- **Target Model**: Trained on the full dataset  
- **Unlearned Model**: Forget set removed using unlearning method (no full retrain)  

### 4. Membership Inference Attack (MIA)  
- Train shadow models to mimic target model  
- Collect prediction confidence scores for members & non-members  
- Train attack model to distinguish between them  

### 5. Metrics  
- **Attack Accuracy** – Higher means easier to identify members  
- **Privacy Gain** – How much harder it is to attack after unlearning  
---



