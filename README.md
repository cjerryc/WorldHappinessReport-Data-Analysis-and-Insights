## Datasets
I have chosen a dataset on the **World Happiness Report** from Kaggle. The dataset spans **five years (2015-2019)** and records happiness survey data for various countries. Each observation represents a **country** and includes features related to factors influencing happiness, such as **Economy** and **Social Support**.

The dataset consists of multiple CSV files, each containing similar columns with slight variations in naming conventions. After **standardizing and cleaning** the data, I have structured it into the following **10 columns**:

- **Country** (Categorical) - Name of the country surveyed
- **Happiness Rank** (Numerical) - The ranking of happiness for a country in a given year
- **Happiness Score** (Numerical) - The calculated happiness index for the country
- **Economy (GDP per Capita)** (Numerical) - Contribution of economic wealth to happiness
- **Social Support** (Numerical) - Perceived level of social support
- **Health (Life Expectancy)** (Numerical) - Contribution of health to happiness
- **Freedom** (Numerical) - Perceived freedom in making life choices
- **Trust (Government Corruption)** (Numerical) - Perceived level of government corruption
- **Generosity** (Numerical) - Contribution of generosity to happiness
- **Year** (Numerical) - The year of the survey

The dataset includes a mix of **numerical** and **categorical** values, with "Country" being the only non-numerical feature. The remaining features describe the extent to which various factors influence happiness in each country.

This data was collected by the **Gallup World Poll**, which surveyed over **150 countries** through representative surveys of approximately **1,000 respondents per country**. Surveys were conducted via **face-to-face interviews or telephone calls**, depending on the country's infrastructure [2].

## Research Questions
Our primary research question is:

> **Do certain features contribute more significantly to higher happiness scores or rankings?**

To expand on this, I will also explore the following secondary questions:

- Does the surveyed rating of one feature affect other rated features?
- Can I predict happiness scores for hypothetical countries based on feature values?
- Which features are the most crucial in determining higher happiness rankings?

To address these questions, I will apply **statistical analysis** and **machine learning models**, such as **K-Nearest Neighbors (KNN) Regression**, to derive insights and make predictions. Our goal is to identify the most influential factors that drive happiness and use our findings to build predictive models for happiness rankings.

# Final Insights and Data Analysis on the World Happiness Report
![Final Poster Insights](https://github.com/cjerryc/WorldHappinessReport-Data-Analysis-and-Insights/blob/main/Data301_FinalPoster.pptx.png?raw=true)


# 🌍 World Happiness Report Analysis (Quickview)

**Jerry Chang**  
*Dr. Allison Theobold, Data 301 Winter 2025*  
California Polytechnic State University, San Luis Obispo

---

## 📌 Introduction / Background / Goals

Happiness and contentment are essential for health—individually and collectively. However, perceptions of happiness vary greatly across cultures. This dataset enables us to analyze predictors of happiness using responses from over 150 countries via the Gallup World Poll.

We aim to answer two main questions:
- **Primary**: Do certain features contribute more greatly to higher happiness scores or rankings?
- **Secondary**: Does the surveyed rating of a predictor affect other predictors?

With this, we explore how predictor interactions can be used to derive happiness scores for hypothetical countries.

---

## 📊 Dataset

**Source**: [World Happiness Report – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness)

- Covers 5 years (2015–2019)
- 1,000 respondents per country, per year
- Collected via face-to-face or telephone interviews depending on infrastructure

---

## 🧹 Data Cleaning & Processing

- Renamed inconsistent column names
- Removed unnecessary columns
- Added a `Year` column
- Merged all five datasets using an outer join
- Filled missing values with `0`

### 📈 Features

- **Response Variables**:  
  - `Happiness Score` (continuous happiness index)  
  - `Happiness Rank` (relative position)

- **Predictors**:  
  - Country  
  - Economy (GDP per Capita)  
  - Social Support  
  - Health (Life Expectancy)  
  - Freedom  
  - Trust (Government Corruption)  
  - Generosity  
  - Year

---

## 🤖 Model

We trained a **K-Nearest Neighbors (KNN) Regression** model using:

- Euclidean Distance
- Distance weighting
- K = 9 (optimal value via GridSearchCV)
- RMSE: **0.524**

The model allows us to predict Happiness Scores based on hypothetical changes in predictor weightings.

### 🔍 Example Insight

> Decreasing Generosity and increasing Social Support (keeping other variables stable) → **Predicted Happiness increased**

---

## 📌 Results & Implications

- **Most influential predictor**: Economy  
- Other key factors: Generosity, Social Support  
- Economy, Generosity, and Social Support had a **negative relationship** with Happiness Score — possibly reflecting societal dissatisfaction with these areas

#### Correlation Analysis

- Strong positive relationship between **Health** and **Economy**
- Moderate positive relationships between **Social Support**, **Economy**, and **Health**

This suggests interconnected influence between societal structures and perceived well-being.

> 🔍 **Policy implication**: Models like this may inform prioritization of social programs or legislative action to increase national morale.

---

## 🧠 Ethics & Limitations

- Cultural and temporal variance in how people perceive happiness
- Surveys are subjective and based on self-reporting
- Limited to respondents with technological access
- Historical and institutional factors skew responses and perceived happiness

📌 **Takeaway**: Results should be interpreted as **supplemental insights**, not definitive guides.

---

## 📷 Figures

### 📉 Figure 1: Predictor Impact on Happiness Score

*(Adjusting predictors by +0.1 and observing change in predicted happiness)*  
🟢 Economy has strongest positive impact  
🔴 Freedom increase leads to slight decrease

![Predictor Impact](https://github.com/cjerryc/WorldHappinessReport-Data-Analysis-and-Insights/blob/main/Predictor%20Impacts.png?raw=true)

---

### 🔄 Figure 2: Correlation Between Predictors

🟢 Strong relationship between Health & Economy  
🟡 Moderate relationship between Social Support and both Economy & Health

![Predictor Correlation](https://github.com/cjerryc/WorldHappinessReport-Data-Analysis-and-Insights/blob/main/Predictor%20Correlations.png?raw=true)

---

## 🙏 Acknowledgements

Special thanks to **Dr. Allison Theobold** for her guidance, and to **Cal Poly SLO** for providing the resources and support for this project.

---

## 📚 References

1. [World Happiness Report – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness)  
2. [How the Gallup World Poll Works](https://www.gallup.com/178667/gallup-world-poll-work.aspx)

