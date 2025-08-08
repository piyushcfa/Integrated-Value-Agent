🤖 Integrated Value AI Agent

Project Overview
Objective: To develop an AI-powered agent that assesses a company's true value by integrating traditional financial data with modern Environmental, Social, and Governance (ESG) metrics.

Methodology: The project evolved through three key phases: 
1) The development of a robust Integrated Value Scorecard to rank companies holistically.
2) The creation of an Interactive Dashboard for data analysis. 
3) The construction of a Predictive Machine Learning Model to forecast future stock performance based on the calculated scores.

Key Result: The final predictive model achieved 59.34% accuracy in forecasting 6-month stock outperformance against the S&P 500, demonstrating that while financial momentum is the primary driver, ESG factors provide a statistically significant predictive edge.

The Problem Statement
Traditional financial metrics like P/E ratios and revenue growth provide an incomplete picture of a company's long-term health and risk profile. In today's market, factors like environmental risk, employee satisfaction, and corporate governance are critical for sustainable growth. This project aimed to build an intelligent tool that moves beyond the traditional, providing a holistic "integrated" valuation to help identify high-quality, resilient companies.

Methodology & The Journey
This project was developed iteratively, with each phase building upon the learnings of the last. It was a comprehensive journey that involved significant debugging and strategic pivots.

Phase 1: Foundational Modeling & Debugging
I began by attempting to build a direct predictive model (Linear and Ridge Regression) for market capitalization using raw financial and ESG data. This initial phase revealed significant real-world statistical challenges:

Data Scaling Issues: Required normalization of all features using StandardScaler.

Model Instability: Required log transformation of the target variable (Market Cap) to handle its vast scale.

Multicollinearity: The model produced nonsensical results when features were highly correlated, a problem solved through careful data curation and, ultimately, by simplifying the model's task.

This rigorous debugging process was critical for building a robust final model.

Phase 2: The Integrated Value Scorecard
Realizing the instability of a direct predictive model with limited public data, I pivoted to a more robust, rules-based scorecard system. This agent calculates a final Integrated_Value_Score by:

Fetching real-time financial data and curated ESG scores.

Normalizing all company metrics to a common 0-100 scale.

Calculating a score for each of the three dimensions: Financial_Score, Environmental_Score, and Social_Score.

Combining these into a final score using a weighted average (50% Financial, 25% Environmental, 25% Social).

Phase 3: The Predictive Engine
The final step was to test the core thesis: "Does a high Integrated Value Score lead to better returns?"
I built a predictive engine using a Random Forest Classifier.

Features: Financial_Score_Proxy, Environmental_Score, Social_Score.

Target: Whether the stock's 6-month return was higher than the S&P 500's return (1 for Outperform, 0 for Underperform).

Dataset: 5 years of historical price data for 20 diverse S&P 500 companies.

Key Results & Analysis
The agent produced two key results: a logical company ranking from the scorecard and a predictive accuracy score from the machine learning model.

1. Predictive Model Accuracy

Metric	Result
Predictive Accuracy	59.34%

Export to Sheets
An accuracy nearly 10 percentage points above a random 50/50 guess demonstrates that the model has legitimate predictive power.

2. Feature Importance

Feature	Importance
Financial_Score_Proxy	93.8%
Social_Score	3.3%
Environmental_Score	2.9%

Export to Sheets
This key insight shows that while financial momentum is the primary driver, ESG factors provide a small but measurable edge in predicting market outperformance.

Technical Stack
Language: Python
Libraries: Pandas, NumPy, Scikit-learn, yfinance, Matplotlib, Ipywidgets
Environment: Google Colab
