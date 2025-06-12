# Amazon Product Return Analysis Using Exponential Distribution

## Introduction
This project explores the analysis of Amazon product returns using the exponential distribution. Understanding product return patterns is crucial for e-commerce businesses to optimize inventory, improve customer satisfaction, and reduce operational costs. Analyzing return data helps identify trends, forecast return rates, and inform business strategies.

## Table of Contents
1. [Data Generation](#data-generation)
2. [Exponential Distributions Implementation](#exponential-distributions-implementation)
3. [Insights](#insights)
4. [Limitations](#limitations)

---

## 1. Data Generation
- **Columns:** `order_id`, `asin`, `category`, `order_date`, `price`, `size_category`, `will_return`, `shipped_month`, `return_date`, `return_days`, `return_reason`, `return_month`, `within_3_months`
- **Rows:** 1000 (synthetic, similar to Amazon product return datasets)
- Synthetic data simulates realistic product return scenarios for analysis.

## 2. Exponential Distributions Implementation

1. **Understanding Exponential Distribution:** Concepts and identification of the rate parameter (lambda).
2. **Kolmogorov-Smirnov (KS) Test:** Validates if the data follows an exponential distribution.
3. **Exponential Probability Density Function (PDF):** Explains PDF vs PMF; for continuous data, probabilities are calculated by integrating the PDF over intervals.
4. **Exponential Cumulative Density Function (CDF):** Calculates the probability of a return within a given time.
5. **Relationship Between PDF and CDF:** The integral of the PDF over an interval equals the difference in CDF values at the interval endpoints.
6. **Exponential Survival Function (SF):** Probability that a return has not occurred by a certain time.
7. **Exponential Percent Point Function (PPF):** Determines the time by which a certain percentage of returns occur.
8. **Memoryless Property:** The probability of return in the future is independent of the time already elapsed.

## 3. Insights

1. **Probability of Return in a Short Interval:** The probability of a product being returned between 29.5 and 30 days is approximately **0.62%** (from PDF over [a, b]).
2. **Probability of Return Within 30 Days:** About **64.27%** of products are returned within 30 days (from CDF at 30 days).
3. **PDF and CDF Consistency:** The integral of the PDF over an interval matches the difference in CDF values, confirming mathematical equivalence (both yield 0.0062 for [29.5, 30] days).
4. **Long-Term Non-Return Probability:** The probability that a product is not returned after 60 days is **12.77%** (from SF).
5. **90% Return Timeframe:** **90%** of returns occur within approximately **67.13 days** (from PPF).
6. **Memoryless Property:** The chance of a product being returned 30 days from now, even after 60 days have passed, is the same as at day 0 (P(X > 90 | X > 60) = P(X > 30) = 35.73%). This illustrates the memoryless nature of the exponential distribution—past elapsed time does not affect future probabilities.
7. **Business Implication:** Most returns happen early, and the likelihood of return drops sharply after the initial period, aiding in inventory and customer service planning.

## 4. Limitations

- The exponential distribution may not fit real-world return data as accurately as other distributions (e.g., Weibull), which can model varying return rates over time.
- Assumes a constant return rate, which may not reflect actual customer behavior.
- Synthetic data may not capture all complexities of real Amazon return patterns.
- Does not account for product-specific or seasonal effects.
