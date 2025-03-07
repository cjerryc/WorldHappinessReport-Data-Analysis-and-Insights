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
