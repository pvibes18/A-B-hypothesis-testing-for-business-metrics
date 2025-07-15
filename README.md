# 📊 A/B Hypothesis Testing: Facebook vs AdWords Campaigns

This project performs **A/B testing and statistical hypothesis testing** to evaluate the effectiveness of two marketing campaigns — **Facebook Ads** and **Google AdWords** — using data from the year 2019.

## 📁 Dataset Description

The dataset contains daily performance metrics for each campaign over one year (365 days per campaign). It includes:

- `Date`: Daily data for the year 2019.
- `Campaign`: "Facebook" or "AdWords"
- `Ad Views`: Number of impressions.
- `Ad Clicks`: Total number of clicks.
- `Ad Conversions`: Total conversions (purchases/sign-ups).
- `Cost per Ad`: Daily ad spend.
- `Click-Through Rate (CTR)`: Clicks / Views
- `Conversion Rate`: Conversions / Clicks
- `Cost per Click (CPC)`: Cost / Clicks

## 🧪 Project Objective

To determine **whether there is a statistically significant difference** between the Facebook and AdWords ad campaigns in terms of:
- Ad Clicks
- CTR
- Conversion Rate
- CPC

Using **hypothesis testing** and **data visualization**, the project aims to answer:
- Is one platform significantly better at engaging users?
- Which platform offers more cost-effective conversions?

## 📊 Exploratory Data Analysis (EDA)

- Distribution plots and boxplots for each key metric.
- Side-by-side comparison between Facebook and AdWords.
- KDE plots to analyze spread and central tendencies.

### Key Insights:
- **Ad Views** and **Ad Clicks** were very similar across platforms.
- Slight differences observed in CTR and Conversion Rates.
- Distribution shapes suggest normal-like behavior, validating t-test usage.

## ✅ Hypothesis Testing

Performed two-sample **independent t-tests** for key metrics:

- **Null Hypothesis (H₀):** No difference in mean metric between Facebook and AdWords.
- **Alternative Hypothesis (H₁):** There is a significant difference.

### Example:

```python
stats.ttest_ind(df[df["Campaign"]=="Facebook"]["Ad Clicks"],
                df[df["Campaign"]=="AdWords"]["Ad Clicks"])
