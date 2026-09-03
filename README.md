# Hotel Booking Cancellation Analysis

## Case Study

### Project Overview

Hotel cancellations can create uncertainty around occupancy, revenue, and operational planning. This project analyzes historical hotel booking data to understand which booking characteristics are associated with cancellations and how those patterns could support better cancellation-risk management.

The analysis focuses on identifying meaningful patterns rather than building a predictive model. The goal is to translate the findings into practical business insights and recommendations.

---

## Business Question

> **What booking characteristics are associated with hotel cancellations, and what can hotels learn from these patterns to support cancellation-risk management?**

---

## Dataset

This project uses the **Hotel Booking Demand** dataset, originally published by Nuno Antonio, Ana Almeida, and Luís Nunes and made available through Kaggle by Jesse Mostipak.

The dataset is licensed under **CC BY 4.0**.

The dataset contains **119,390 hotel bookings** across **32 variables** and covers two hotel types: **City Hotel** and **Resort Hotel**.

Each record represents an individual hotel booking and contains information about the hotel, booking characteristics, customer history, deposit type, market segment, scheduled arrival, and reservation outcome.

The primary outcome variable is `is_canceled`, which indicates whether a booking was canceled or resulted in a no-show.

**Source:** [Hotel Booking Demand Dataset on Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

**Original publication:** Antonio, N., de Almeida, A., & Nunes, L. (2019). *Hotel booking demand datasets*. Data in Brief, 22, 41–49. https://doi.org/10.1016/j.dib.2018.11.126

---

## Tools Used

- **Python**
- **Pandas** – data manipulation and analysis
- **NumPy** – numerical operations
- **Matplotlib** – data visualization
- **Jupyter Notebook** – analysis environment

---

# Analysis Approach

The analysis examined cancellation behavior across several booking characteristics, including hotel type, lead time, deposit type, market segment, previous cancellation history, cancellation timing, arrival seasonality, and combinations of booking characteristics.

Cancellation rates were calculated across different groups and supported with visualizations to identify the strongest and most meaningful patterns.

The analysis was intentionally focused on identifying **associations rather than causation**.

---

# Key Findings

## 1. Deposit Type Was the Strongest Observed Difference

Deposit type showed the largest observed difference in cancellation behavior.

Non Refund bookings had a **99.36%** cancellation rate, compared with **28.38%** for No Deposit bookings and **22.22%** for Refundable bookings.

The extremely high cancellation rate observed for Non Refund bookings is specific to this dataset and should not be interpreted as evidence that the deposit policy itself causes cancellations.

## 2. Previous Cancellation History Was a Strong Risk Indicator

Bookings from customers with at least one previous cancellation had a **91.64%** cancellation rate, compared with **33.91%** for bookings with no previous cancellation history.

This suggests that previous booking behavior may provide useful information when assessing the risk of a future cancellation.

## 3. Longer Lead Times Were Associated With Higher Cancellation Rates

Cancellation rates increased substantially as bookings were made further in advance.

Bookings made **0–30 days** before arrival had an **18.56%** cancellation rate, while bookings made **366 or more days** in advance had a **67.66%** cancellation rate.

This pattern was observed across both hotel types and suggests that cancellation risk may be identifiable relatively early in the reservation lifecycle rather than only shortly before arrival.

## 4. Multiple Risk Characteristics Can Overlap

The analysis combined three characteristics that showed strong individual associations with cancellation: previous cancellation history, Non Refund deposit type, and a lead time of at least 181 days.

This identified **2,405 bookings**, all of which were recorded as canceled or no-show.

This provides additional supporting evidence that multiple high-risk characteristics can overlap within the same bookings. The result was treated as an observed high-risk segment in this dataset rather than as a validated predictive rule.

## 5. Cancellations Occurred Throughout the Booking Lifecycle

Among the **43,017 bookings** whose final reservation status was `Canceled`, the median cancellation occurred **56 days before the scheduled arrival date**.

Approximately **33.71%** of cancellations occurred within 30 days of arrival, while approximately **36.14%** occurred 91 or more days before arrival.

This indicates that cancellations were not concentrated exclusively in the final days before arrival.

---

# Additional Findings

Cancellation behavior also differed across hotel type, market segment, and arrival month.

**City Hotel** recorded a **41.73%** cancellation rate, compared with **27.76%** for Resort Hotel.

Among the major market segments, **Groups** had the highest observed cancellation rate at **61.06%**, while **Direct** bookings had a much lower rate of **15.34%**.

Seasonality was also observed. Overall cancellation rates ranged from **30.48% in January** to **41.46% in June**. However, this variation was smaller than the differences observed for deposit type, previous cancellation history, and lead time.

---

# Business Insights

The analysis suggests that cancellation risk is not evenly distributed across hotel bookings.

The strongest observed patterns were associated with **deposit type, previous cancellation history, and lead time**. These characteristics may provide useful signals for identifying bookings that warrant closer attention.

The combined-risk analysis further suggests that several high-risk characteristics can overlap within the same reservation.

The cancellation-timing analysis also indicates that cancellation-management efforts should not focus exclusively on the final days before arrival.

---

# Business Recommendations

## 1. Identify High-Risk Bookings Earlier

Hotels could use information available at the time of booking, such as lead time, deposit type, and previous cancellation history, to identify bookings that may have a higher likelihood of cancellation.

Early identification could allow staff to monitor potentially high-risk bookings throughout the reservation lifecycle rather than waiting until the arrival date approaches.

## 2. Prioritize Bookings With Multiple Risk Characteristics

Bookings that combine several high-risk characteristics could receive greater attention than bookings showing only one risk indicator.

The combination identified in this analysis could serve as an example of how hotels might group bookings for closer monitoring, while recognizing that the observed pattern would need to be validated with future data.

## 3. Monitor Cancellation Risk Throughout the Booking Lifecycle

Because cancellations occurred well before arrival as well as closer to the arrival date, cancellation-management efforts should not be limited to the final days before arrival.

Hotels could establish periodic monitoring of higher-risk bookings to identify changes and respond earlier when appropriate.

## 4. Review the Non Refund Booking Category

The exceptionally high cancellation rate observed among Non Refund bookings warrants further investigation.

Hotels could examine whether factors such as booking channels, customer behavior, pricing, policy structure, or data-recording practices contribute to the observed pattern.

The goal should not be to assume that the Non Refund policy causes cancellations, but rather to investigate why this category has such a different cancellation outcome from other deposit types.

## 5. Use Booking Characteristics to Support Operational Decision-Making

Cancellation-risk indicators could potentially support decisions related to occupancy planning, inventory management, reservation monitoring, and booking policies.

Any such approach should be tested against future booking data before being relied upon for operational decisions.

---

# Limitations

## 1. The Analysis Shows Associations, Not Causation

The analysis identifies relationships between booking characteristics and cancellation outcomes, but it does not establish that one factor causes another.

For example, Non Refund bookings had an exceptionally high observed cancellation rate, but the analysis cannot determine whether the deposit policy itself caused this outcome. Other factors, such as lead time, market segment, distribution channel, or booking practices, may also contribute to the observed relationship.

## 2. Results Are Specific to This Dataset

The findings are based on this historical dataset and should not automatically be generalized to other hotels, locations, or time periods.

For example, the **99.36%** cancellation rate observed for Non Refund bookings is a characteristic of this dataset and may not represent cancellation behavior in other hotel environments.

## 3. Some Categories Have Small Sample Sizes

Certain categories contain relatively few observations, making their results less reliable for comparison.

For example, the Refundable deposit category contains only **162 bookings**, while the Undefined market segment contains only **two bookings**. Findings involving these small groups should therefore be interpreted with caution.

## 4. Limited Information About Booking Creation and Operational Processes

The dataset does not contain detailed information about customer motivations, hotel operational decisions, booking management, or the full booking creation process.

As a result, the analysis cannot determine why certain booking characteristics are associated with higher cancellation rates or explain the operational processes behind the observed patterns.

## 5. The High-Risk Profile Is an Observed Pattern

The combined high-risk profile showed a **100% unfavorable outcome** among the 2,405 matching bookings.

However, this does not mean that every future booking with these characteristics will necessarily be canceled or become a no-show. The result should be interpreted as an observed pattern within this dataset rather than a validated predictive model.

---

# Conclusion

This analysis examined **119,390 hotel booking records** to understand which booking characteristics were associated with cancellations and what hotels could learn from those patterns.

The strongest observed differences were associated with **deposit type, previous cancellation history, and lead time**. Non Refund bookings had a **99.36%** cancellation rate, bookings from customers with previous cancellations had a **91.64%** cancellation rate, and cancellation rates increased from **18.56%** for bookings made 0–30 days before arrival to **67.66%** for bookings made 366 or more days in advance.

The analysis also showed that multiple high-risk characteristics can overlap within the same bookings and that cancellations can occur well before the scheduled arrival date.

From a business perspective, these findings suggest that hotels could potentially improve cancellation-risk management by identifying higher-risk bookings earlier and monitoring them throughout the reservation lifecycle.

However, the results represent **associations observed in historical data**, not causal relationships or guaranteed predictions for future bookings.

---

# Project Structure

hotel-booking-cancellation-analysis/
│
├── data/
│   └── raw/
│       └── hotel_bookings.csv
│
├── notebooks/
│   └── hotel_booking_cancellation_analysis.ipynb
│
├── output/
│   └── charts/
│
├── README.md
├── requirements.txt
└── .gitignore

## Author

**Ahmed Baqa**

Data Analytics Portfolio Project
