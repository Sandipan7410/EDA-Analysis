# Customer Behaviour & Churn Analysis (Python EDA)

Exploratory analysis of 500 customers across five Indian cities to find out how they buy and how many are slipping away, ending in a recency segmentation and a targeted retention recommendation.

[Open the notebook](EDA.ipynb)

## Key findings

| Segment (days since last purchase) | Customers | Share | Total spend |
| --- | --- | --- | --- |
| Active (≤180) | 30 | 6% | ₹75.5K |
| At risk (181–365) | 75 | 15% | ₹1.98 lakh |
| Lapsed (>365) | 395 | 79% | ₹10.0 lakh |

- **79% of customers haven't bought in over a year.** Only 6% bought in the last six months.
- **The 75 at-risk customers are the opportunity:** recent enough for a win-back offer, with ₹1.98 lakh of past spend.
- **Lapsing isn't driven by spend or satisfaction.** Average spend (₹2,500–2,650) and feedback (2.8–3.0 out of 5) barely differ between segments, so customers need a reason to come back, such as reminders or offers.
- **Feedback is middling overall** at 2.9 out of 5, which deserves its own investigation.

**Recommendation:** run a win-back campaign for the at-risk segment and track the 60-day return rate.

## Approach

1. **Cleaning:** filled 25 missing values each in age and feedback (mean) and purchase amount (median); checked duplicates and data types.
2. **Univariate analysis:** distributions, skewness and outliers for age, spend and feedback; frequency counts for gender and city.
3. **Purchase timing:** date ranges, gaps between purchases, a seasonal decomposition and a day-by-month heatmap.
4. **Churn:** recency from the latest purchase date. A 90-day rule would flag 98% of customers because the data spans three years, so customers are grouped into Active, At risk and Lapsed instead.

## Tools

Python · Pandas · Matplotlib · Seaborn · Statsmodels · Jupyter

## Run it

```bash
pip install -r requirements.txt
jupyter notebook EDA.ipynb
```

## Data note

The dataset is synthetic (`customer_data.csv`). Some names and genders don't match, so gender comparisons are illustrative only. It records only each customer's last purchase, so a full RFM model would need purchase history.
