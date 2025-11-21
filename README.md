# **AI Ethics: COMPAS Algorithm Bias Audit**

## **📋 Project Overview**

This project conducts a comprehensive fairness audit of the COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) recidivism algorithm, which gained notoriety for demonstrating racial bias in criminal risk assessments. The analysis implements ethical AI principles using IBM's AI Fairness 360 toolkit to measure, visualize, and attempt to mitigate algorithmic discrimination.

## **🎯 Objectives**
Measure Racial Bias: Quantify disparities in COMPAS risk scores between Caucasian and non-Caucasian defendants

Implement Mitigation: Apply fairness-aware machine learning techniques to reduce bias

Evaluate Effectiveness: Assess whether bias mitigation strategies improve equity

Provide Recommendations: Suggest technical and policy solutions for fairer AI systems

## **📊 Dataset**

**Source:** ProPublica's COMPAS Analysis

 | File | Records | Timeframe | Key Variables |
| :--- | :---: | :---: | :--- |
| compas-scores-two-years.csv | 6,172 defendants | 2013-2014 | race, two_year_recid, decile_score |

**Data Encoding:**

- race: 1.0 = Caucasian, 0.0 = Non-Caucasian

- two_year_recid: 1 = re-offended, 0 = did not re-offend

- decile_score: COMPAS risk score (1-10)

## **🛠️ Technical Requirements**

Python Libraries
bash
pip install aif360 pandas matplotlib scikit-learn

**Core Dependencies**

- AI Fairness 360 (v0.5.0+) - IBM's comprehensive fairness toolkit

- Pandas - Data manipulation and analysis

- Matplotlib - Data visualization

- Scikit-learn - Machine learning models

## **🚀 Quick Start**

1. **Clone and Setup**
   
bash
git clone <repository-url>
cd compas-bias-audit
pip install -r requirements.txt

2. **Run the Analysis**
   
bash
python compas_fairness_audit.py

3. **View Results**
   
- Console output with fairness metrics

- Visualization of False Positive Rate disparities

- Generated report in compas_analysis_report.pdf

 ## 📊 Bias Metrics Analysis Table

| Metric | Initial Value | Interpretation | Post-Mitigation Value | Change |
| :--- | :---: | :--- | :--- | :---: |
| **Initial Bias Metrics** | | | | |
| Disparate Impact | 0.818 | Substantial bias (ideal = 1.0) | 0.795 | ❌ Worsened |
| Statistical Parity Difference | -0.116 | Significant disparity | -0.125 | ❌ Increased disparity |
| **Post-Mitigation Results** | | | | |
| Equal Opportunity Difference | - | - | -0.026 | - |
| Average Odds Difference | - | - | -0.013 | - |

## **🚨 Critical Insight**
The Reweighing mitigation technique unexpectedly increased bias in this implementation, highlighting the complexity of algorithmic fairness interventions.

## **🔍 Methodology**

1. **Data Preprocessing**
   
- Filtered records using ProPublica's criteria

- Encoded race as binary protected attribute

- Handled missing values and data validation

2. **Bias Measurement**
   
- Disparate Impact Ratio

- Statistical Parity Difference

- Equal Opportunity Difference

- Average Odds Difference

3. **Mitigation Techniques**
- Reweighing (Pre-processing)

- Logistic Regression classifier

- Fairness metrics comparison

## **🎨 Visualizations**

The analysis generates:

- **False Positive Rate Disparity Chart:** Comparing error rates between racial groups

- **Fairness Metrics Comparison:** Pre- vs post-mitigation results

- **Demographic Distribution:** Dataset composition analysis

## **📝 Report Contents**

The comprehensive audit report includes:

1. **Executive Summary** - Key findings and implications

2. **Methodology** - Technical approach and fairness metrics

3. **Results Analysis** - Detailed metric interpretation

4. **Mitigation Challenges** - Analysis of failed bias correction

5. **Recommendations** - Technical and policy solutions

6. **Ethical Considerations** - Broader societal implications

## **⚠️ Limitations & Challenges**

- **Binary Race Classification:** Simplified racial categories may mask intersectional biases

- **Mitigation Failure:** Reweighing technique worsened disparities in this case

- **Historical Data:** Inherits biases from past judicial decisions

- **Model Complexity:** Simple logistic regression may not capture nuanced relationships

## **🔮 Future Work**

- Test alternative mitigation algorithms (Prejudice Remover, Adversarial Debiasing)

- Implement intersectional fairness analysis

- Develop real-time bias monitoring dashboards

- Create policy guidelines for judicial AI deployment

## **📚 References**
1. ProPublica (2016). "Machine Bias" - Original investigation

2. IBM AI Fairness 360 Documentation

3. EU Ethics Guidelines for Trustworthy AI

4. COMPAS Technical Documentation

## **📄 License**
Educational use - Based on ProPublica's publicly available data and analysis.
