
# 🚀 Consumer Behavior Analytics & Predictive "Whale" Scoring



## 📌 Executive Summary



This project transforms raw ecommerce transaction data into actionable customer intelligence. By moving beyond standard reporting, we identified a critical misalignment in the company's loyalty program and built a **Predictive "Whale" Engine**.



Using a **Random Forest Classifier**, we scored every customer on their propensity to be a High-Value Shopper (Top 25%), creating a targeted list of **112 VIPs** who represent **$46,365 in immediate revenue risk**.



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



### 2. "Whale" Profiling (Top 10% Spenders) 🐋



We isolated the elite 10% of the customer base to understand their habits.



* **Demographics:** Predominantly **Female, aged 30-35**.

* **Top Categories:** **Baby Products, Clothing, and Electronics**.

* **Shopping Channel:** They are **Omnichannel** shoppers (engaging both Online and Offline) rather than single-channel users.



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



1. **Clone the Repository**

```bash

git clone https://github.com/yourusername/consumer-behavior-analytics.git



```





2. **Install Requirements**

```bash

pip install pandas numpy matplotlib seaborn plotly scikit-learn



```





3. **Launch the Notebook**

```bash

jupyter notebook Consumer_Behavior_Project.ipynb



```







---



## 📈 Future Recommendations



Based on the data, the following business actions are recommended:



1. **Restructure Loyalty:** Move from "Points per Visit" to "Points per Dollar" to reverse the negative CLV trend.

2. **Target the 30-35 Demographic:** Shift ad spend for Baby Products/Electronics to this high-conversion age group.

3. **Deploy the "Consumer Dict":** Integrate the JSON output into the email marketing platform to trigger automatic "VIP Outreach" emails when a user's Propensity Score > 0.6.



---



*Author: Daniel Ohebshalom*
