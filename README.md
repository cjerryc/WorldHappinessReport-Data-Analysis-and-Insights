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


# World Happiness Report Analysis (Quickview)

**Jerry Chang**  
*Dr. Allison Theobold, Data 301 Winter 2025*  
California Polytechnic State University, San Luis Obispo

---

## Introduction / Background / Goals

Happiness and contentment are essential for health—individually and collectively. However, perceptions of happiness vary greatly across cultures. This dataset enables us to analyze predictors of happiness using responses from over 150 countries via the Gallup World Poll.

We aim to answer two main questions:
- **Primary**: Do certain features contribute more greatly to higher happiness scores or rankings?
- **Secondary**: Does the surveyed rating of a predictor affect other predictors? Within this data, we could also derive predicted happiness scores of hypothetical countries, depending on a collection of features.

With this, we explore how predictor interactions can be used to derive happiness scores for hypothetical countries.

This data [1] was collected by the Gallup World Poll from over 150 countries, using representative surveys of about 1,000 respondents per country. Surveys are done via face-to-face interviews or telephone calls, depending on the country's infrastructure [2]

---

## Dataset

**Source**: [World Happiness Report – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness)

- Covers 5 years (2015–2019).
- 1,000 respondents per country, per year.
- Collected via face-to-face or telephone interviews depending on infrastructure.
- A mix of numerical values and categorical values.

---

## Data Cleaning & Processing

- Renamed inconsistent column names.
- Removed unnecessary columns.
- Added a `Year` column.
- Merged all five datasets using an outer join.
- Filled missing values with `0`.
- Model Tuning: Scale with Mean and without Standard Deviation, use Euclidean Distance, use K= 9 Neighbors in KNN, and weight by Distance.


### Features

- **Response Variables**:  
  - `Happiness Score` (continuous happiness index) describes the calculated happiness index for that country in that year.
  - `Happiness Rank` (relative position) describes the ranking of Happiness of a country that year.

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

## Model

We trained a **K-Nearest Neighbors (KNN) Regression** model using:

- Euclidean Distance
- Distance weighting
- K = 9 (optimal value via GridSearchCV)
- RMSE: **0.524**
  
We have chosen to train a KNN-Regression model for this data. Based on the combination of features, we predict a numerical score on a continuous scale. Using GridSearchCV, we were able to tune hyperparameters to find an ideal KNN model for the dataset for an RMSE of 0.524. 

Using the tuned model, we may predict happiness for hypothetical weightings and regions to better understand how increasing the focus on a feature would perform for overall happiness. For example, when decreasing the weighting for Generosity and shifting that sum to increase the weighting for Social Support, we found that predicted Happiness increased for the hypothetical case, keeping all other predictors stable.


### Example Insight

> Decreasing Generosity and increasing Social Support (keeping other variables stable) → **Predicted Happiness increased**

---

## Results & Implications

- **Most influential predictor**: Economy  
- Other key factors: Generosity, Social Support  
- Economy, Generosity, and Social Support had a **negative relationship** with Happiness Score — possibly reflecting societal dissatisfaction with these areas

#### Correlation Analysis

- Strong positive relationship between **Health** and **Economy**
- Moderate positive relationships between **Social Support**, **Economy**, and **Health**

This suggests interconnected influence between societal structures and perceived well-being.

> **Policy implication**: Models like this may inform prioritization of social programs or legislative action to increase national morale.

From our KNN regression model with K = 9, Euclidean Distance, and Distance weighting, we have found that emphasis on the Economy is the most influential predictor on a country’s overall happiness.
- Other influential predictors: Generosity, Social Support. 
- Economy, Generosity, and Social Support have a negative relationship with Happiness Score, which may potentially be explained by negative sentiment that results in higher weightings for those features and poor effects on a people’s Happiness.

From calculating correlations between Predictors, we find some strong correlations
- A strong, positive relationship between the importance of Health and the Economy when deciding on Happiness in a country. 
- This reflects an underlying effect predictors have on each other in rating Happiness.

This model could potentially be used to identify social programs or legislation that governmental bodies could prioritize to lift morale and address the grievances of their constituents, or to place a country amongst rankings on happiness.

A limitation is that the change in what citizens of a country hold to be important could shift dramatically between years, at a rate faster than what annually collected data reflects and much faster than the action of legislation.

---

## Ethics & Limitations

- Cultural and temporal variance in how people perceive happiness
- Surveys are subjective and based on self-reporting
- Limited to respondents with technological access
- Historical and institutional factors skew responses and perceived happiness

Happiness and contentment are essential for our health as individuals and as a collective. Without happiness of some level, our health would suffer and would reflect in our communities. That being said, different cultures perceive happiness differently between self and society, community, or even within. This dataset does not capture the fine grained reasons for happiness in different countries, and thus we may only interpret happiness in terms of the available predictors. 

Historical events greatly affect the societal stratification of a people, the wealth amongst the people, and perception on a global scale. When we view predictors such as GDP and Government Corruption, we must understand that people make do within their setting to find their happiness. 

Institutions in a country affect the educational, racial, political, monetary, etc. opportunities respondents have, and in turn, would affect goals necessary for happiness. This skews the data on an individual level and if the respondents are not varied, this would be reflected for the perceived happiness of the overall country and in the weighting in an observation.

Furthermore, these ratings are done based on feeling rather than hard, repeatable measurements and are thus subject to human bias. The types of respondents are those technologically reachable, and this could skew the scores and importance since it is a voluntary survey. With all these factors in mind, our findings should be taken as reference or supplemental information, rather than an absolute guide for interested parties.


**Takeaway**: Results should be interpreted as **supplemental insights**, not definitive guides.

---

## Figures

### Figure 1: Predictor Impact on Happiness Score

*(Adjusting predictors by +0.1 and observing change in predicted happiness)*  
🟢 Economy has strongest positive impact  
🔴 Freedom increase leads to slight decrease

![Predictor Impact](https://github.com/cjerryc/WorldHappinessReport-Data-Analysis-and-Insights/blob/main/Predictor%20Impacts.png?raw=true)

Looking at the changes in Happiness Scores after adjusting each predictor by a 0.1 increase, we may see that people's perception of the Economy is the most influential predictor for Happiness Scores of a country. For a 0.1 increase in weighting for Freedom, there is an associated 0.0339 decrease in Happiness Score, while holding all other variables 

---

### Figure 2: Correlation Between Predictors

🟢 Strong relationship between Health & Economy  
🟡 Moderate relationship between Social Support and both Economy & Health

![Predictor Correlation](https://github.com/cjerryc/WorldHappinessReport-Data-Analysis-and-Insights/blob/main/Predictor%20Correlations.png?raw=true)

To answer our secondary question, we calculate the correlation between all the different predictors across the years. There is a strong, positive relationship between the importance of Health and the Economy when rating Happiness in a country. There is a moderately strong, positive relationship between the importance of Social Support and both Economy and Health.

---

## Acknowledgements

Special thanks to **Dr. Allison Theobold** for her guidance, and to **Cal Poly SLO** for the resources provided for learning in DATA 301.


---

## 📚 References

1. [World Happiness Report – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness)  
2. [How the Gallup World Poll Works](https://www.gallup.com/178667/gallup-world-poll-work.aspx)

