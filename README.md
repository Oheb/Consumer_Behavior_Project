
# 🚀 Consumer Behavior Analytics & Predictive "Whale" Scoring



## 📌 Executive Summary

This project moves beyond standard reporting to answer the critical question: **Who are our most valuable customers, and how do we find more of them?**

Using a dataset of 1,000 ecommerce transactions, we performed a deep-dive analysis to identify "Whale" customers, debug the underperforming Loyalty Program, and build a Random Forest Classifier that predicts high-value potential in new users.

## 🚨 Critical Findings

### 1. The Loyalty Paradox
Non-Members are surprisingly more valuable (**$2,020 CLV**) than Loyalty Members (**$1,797 CLV**). This counterintuitive finding suggests the loyalty program may need restructuring to deliver genuine value.

### 2. The "Device Myth" Busted
Mobile users spend nearly identical amounts per cart as Desktop users. **Do not downgrade the mobile experience** — both channels are equally critical to revenue.

### 3. Age is Irrelevant
There is zero correlation (R² = 0.0003) between age and spending. A 20-year-old is just as likely to drop $500 as a 50-year-old. Age-based segmentation is not recommended for this customer base.

---



## 🔍 Key Strategic Insights



### 1. The Loyalty Paradox 🚨



Our analysis revealed a counter-intuitive trend: **Non-Members are more valuable than Loyalty Members.**



* **Insight:** Loyalty members use discounts 54% of the time (vs 49% for non-members) and have a lower average basket size.

* **Business Impact:** The current program incentivizes "discount seeking" rather than high-value purchasing.



| Metric | Loyalty Members | Non-Members |

| --- | --- | --- |

| **Avg Lifetime Value (CLV)** | $1,797 | **$2,020** 🏆 |

| **Discount Usage Freq** | 54% | 49% |

| **Avg Spend per Order** | $261 | $288 |



### 2. "Whale" Profiling  🐋



### 1. The "Deep Dive" Whale (Top 10%)
- **Used In:** The initial Exploratory Data Analysis (EDA) and Dashboards
- **Definition:** The absolute top 10% of spenders
- **Purpose:** To profile the "Elite" customer
- **Key Traits:** Female, Aged 30-35, buying Electronics & Baby Products

### 2. The "Predictive" Whale (Top 25%)
- **Used In:** The Random Forest Model & Consumer Dictionary
- **Definition:** The top 25% of spenders (Spend > ~$418)
- **Purpose:** To train the Machine Learning model (ML models need more "positive" examples to learn effectively)
- **Output:** Any customer with a Propensity Score > 0.60 is flagged for "VIP Outreach"




### 3. Myth Busting: Age & Income



* **Age vs. Spend:** There is **zero correlation (R² = 0.0003)** between age and spending power. A 20-year-old is just as likely to spend $500 as a 50-year-old.

* **The Device Gap:** Myth busted. Mobile users spend nearly identical amounts per cart as Desktop users.



---



## 🤖 The Predictive Model



We engineered a machine learning pipeline to predict high-value potential based on demographic traits, allowing marketing to target users *before* they make a purchase.



* **Model:** Random Forest Classifier (`n_estimators=100`)

* **Target:** Top 25% of Spenders (Threshold: >$418/order)

* **Features:** `Age`, `Gender`, `Income_Level`, `Education_Level`

* **Performance:** Strong positive correlation (**R² = 0.81**) between predicted propensity scores and actual spending.



### Interactive Analysis



The project includes a **Plotly Interactive Scatterplot** allowing stakeholders to hover over customers to see real-time predictive scores.



*(Note: Correlation between Actual Spend and Predicted Whale Propensity)*



---



## 📂 The "Consumer Dictionary"



Instead of a static CSV, the final output of this project is a structured **JSON-style Intelligence Profile** for every customer. This structure is designed to be fed directly into a CRM or Marketing API.



**Sample Entry:**



```json

"37-611-6911": {

    "Profile": {

        "Age": 22,

        "Gender": "Female",

        "Location": "Évry"

    },

    "Metrics": {

        "Top_Cat": "Gardening & Outdoors",

        "Spend": 333.80,

        "Loyalty_Level": 5

    },

    "Predictions": {

        "Whale_Propensity": 0.892,

        "Recommended_Action": "VIP Outreach"

    }

}



```



---



## 🛠️ Technical Implementation



### Data Pipeline



1. **Cleaning:** Removed currency symbols (`$`), handled nulls, and converted data types.

2. **Feature Engineering:** Created `CLV_Score` (Spend × Frequency) and 5-Year Age Bins.

3. **Encoding:** Applied One-Hot Encoding to categorical variables (Gender, Education).



### Libraries Used



* **Pandas:** Data manipulation and aggregation.

* **Seaborn:** Static statistical visualizations (Boxplots, Heatmaps).

* **Plotly Express:** Interactive, hover-able web charts.

* **Scikit-Learn:** Random Forest implementation.



---



## 🚀 How to Run


1. **Install Requirements**

```bash

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

```



2. **Launch the Notebook**

```bash

jupyter notebook Consumer_Behavior_Project.ipynb

```


3. **Download the CSV Used in This Project**

This can be found [here](https://www.kaggle.com/datasets/salahuddinahmedshuvo/ecommerce-consumer-behavior-analysis-data?resource=download) (Kaggle account may be required)




---



## 📈 Future Recommendations



Based on the data, the following business actions are recommended:



1. **Restructure Loyalty:** Move from "Points per Visit" to "Points per Dollar" to reverse the negative CLV trend.

2. **Target the 30-35 Demographic:** Shift ad spend for Baby Products/Electronics to this high-conversion age group.

3. **Deploy the "Consumer Dict":** Integrate the JSON output into the email marketing platform to trigger automatic "VIP Outreach" emails when a user's Propensity Score > 0.6.



---







*Author: Daniel Ohebshalom*
