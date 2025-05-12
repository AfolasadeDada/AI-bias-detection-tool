# AI-bias-detection-tool
# Fairness in Income Prediction (Adult Dataset)

This project investigates fairness in machine learning by analyzing bias in income prediction models. Using the UCI Adult Income dataset, the goal is to predict whether an individual earns more than $50K per year—while ensuring that the model does not unfairly favor or disadvantage individuals based on sensitive attributes such as sex.

## Problem Statement

Traditional machine learning models are often evaluated based on metrics like accuracy, precision, or recall. However, these metrics do not capture whether the model behaves differently for different groups of people. For example, a model may be highly accurate overall, but disproportionately misclassify individuals based on gender, race, or age.

This project aims to identify and reduce such bias. The focus is on measuring fairness in predictions across different gender groups and applying bias mitigation strategies to create a more equitable model.

## Dataset

The dataset used is the Adult Income dataset from the UCI Machine Learning Repository. It includes various demographic and employment-related attributes such as:

- Age  
- Workclass  
- Education  
- Marital status  
- Occupation  
- Race  
- Sex  
- Hours worked per week  
- Native country

The target variable is binary: whether the individual's income exceeds $50K per year.

## Techniques and Tools Used

To evaluate and improve fairness in our predictions, the following tools and techniques were used:

- **Libraries and Frameworks**:  
  - scikit-learn for modeling  
  - pandas and matplotlib for data analysis and visualization  
  - AIF360 (AI Fairness 360) for fairness metrics and bias mitigation

- **Model**: Logistic Regression was used as a baseline classifier.

- **Fairness Metrics**:  
  - *Disparate Impact*: Measures whether outcomes are equally distributed across groups  
  - *Equal Opportunity Difference*: Compares true positive rates between groups  
  - *Average Odds Difference*: Averages differences in both true positive and false positive rates between groups

- **Bias Mitigation Strategy**:  
  - *Reweighing*: A preprocessing technique that assigns weights to training instances in order to balance representation and reduce bias before training the model

## Results Summary

Fairness metrics were computed before and after applying the bias mitigation technique. The following table summarizes the impact:

| Metric                    | Before     | After      |
|---------------------------|------------|------------|
| Disparate Impact          | 0.28       | 1.01       |
| Equal Opportunity Diff.   | -0.164     | 0.0072     |
| Average Odds Difference   | -0.118     | 0.0046     |

These results demonstrate a significant improvement in fairness across all evaluated metrics after applying the reweighing method.

## Visual Analysis

To further evaluate model fairness and performance, several visualizations were generated:

- **Disparate Impact Bar Chart**: To visualize bias reduction before and after mitigation
- ![Screenshot 2025-04-19 003802](https://github.com/user-attachments/assets/c7b9d3e9-fb19-42f4-b1bf-e8f4ad39092e)
![Screenshot 2025-04-19 003835](https://github.com/user-attachments/assets/b0698a1a-94e9-4c1c-ba2c-394971d71e5c)

- **Confusion Matrices by Group**: To analyze true and false classifications across groups

## How to Use This Project

To explore or reproduce this analysis:

1. Open the project in Google Colab or your local environment  
2. Install the required libraries (e.g., AIF360, scikit-learn)  
3. Run the notebook step-by-step to see the preprocessing, model training, fairness evaluation, and mitigation


## Future Enhancements

There are several ways this project could be extended:

- Evaluate bias across other sensitive attributes such as race, age, or education level  
- Apply alternative mitigation techniques such as adversarial debiasing or post-processing methods  
- Deploy an interactive Streamlit app to allow users to test the model in real time  
- Write a detailed blog post to share the methodology and findings with a broader audience

## Conclusion

Fairness in machine learning is critical, especially when models are used to make decisions that impact people’s lives. This project demonstrates how fairness metrics can expose hidden bias and how mitigation strategies can lead to more equitable outcomes, without sacrificing overall performance.

