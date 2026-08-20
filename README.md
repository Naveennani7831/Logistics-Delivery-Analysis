# Logistics Delivery Analysis

## Project Overview

This project analyzes logistics delivery data to understand delivery performance, delays, costs, customer satisfaction, and delivery patterns.

The analysis uses **Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, and K-Means clustering**. A Random Forest Regression model is also used to predict delivery time.

## Dataset

- **Rows:** 25,000
- **Final CSV:** `Logistics_Delivery_Final.csv`
- **Main target:** `delivery_time_hours`

### Important columns

| Column | Description |
|---|---|
| `delivery_id` | Unique delivery identifier |
| `delivery_partner` | Delivery partner |
| `package_type` | Type of package |
| `vehicle_type` | Vehicle used for delivery |
| `delivery_mode` | Delivery mode |
| `region` | Delivery region |
| `weather_condition` | Weather condition |
| `distance_km` | Delivery distance in kilometers |
| `package_weight_kg` | Package weight |
| `delivery_time_hours` | Actual delivery time |
| `expected_time_hours` | Expected delivery time |
| `delayed` | Whether the delivery was delayed |
| `delivery_status` | Delivery status |
| `delivery_rating` | Customer rating |
| `delivery_cost` | Delivery cost |
| `delay_hours` | Actual delivery time minus expected delivery time |
| `cluster` | K-Means cluster assigned to the delivery |

## Project Workflow

1. Data loading and exploration
2. Data type and missing-value checks
3. Data cleaning and validation
4. Delivery-time correction
5. Delay analysis
6. Logistics KPI calculation
7. Random Forest Regression
8. K-Means clustering
9. Cluster analysis and visualization
10. Final CSV export

## Key Logistics KPIs

From the final analysis:

- **Total deliveries:** 25,000
- **Delay rate:** 26.68%
- **On-time delivery rate:** 73.32%
- **Average actual delivery time:** 6.25 hours
- **Average expected delivery time:** 13.11 hours
- **Average delivery cost:** 864.94
- **Average customer rating:** 3.67

### Delay interpretation

`delay_hours` is calculated as:

`actual delivery time - expected delivery time`

Therefore, a negative value means the delivery was completed earlier than expected, while a positive value means it took longer than expected.

The overall average `delay_hours` is negative because many deliveries were completed earlier than their expected time. The separate `delayed` flag is used to calculate the operational delay rate.

## Machine Learning — Random Forest Regression

The Random Forest Regression model was evaluated using:

- **MAE:** 1.34 hours
- **RMSE:** 1.69 hours
- **R²:** 0.704

### Model interpretation

An R² score of **0.704** means the model explains approximately **70.4% of the variation in delivery time** on the test data.

The MAE of **1.34 hours** means that, on average, the model's predicted delivery time differs from the actual delivery time by about 1.34 hours.

## Customer and Operational Insights

The analysis can help identify:

- Factors associated with longer delivery times
- Deliveries that are more likely to be delayed
- Differences between actual and expected delivery times
- Cost and customer-rating patterns
- Distinct delivery groups using clustering

## K-Means Clustering

K-Means clustering was used to group deliveries based on operational characteristics including:

- Delivery time
- Expected delivery time
- Distance
- Package weight
- Delivery cost
- Customer rating

The final analysis produced **4 delivery clusters**.

### Cluster summary

| Cluster | Avg Delivery Time | Avg Expected Time | Avg Distance (km) | Avg Cost | Avg Rating |
|---:|---:|---:|---:|---:|---:|
| 0 | 9.21 h | 7.06 h | 221.43 | 1252.18 | 2.24 |
| 1 | 3.98 h | 5.56 h | 76.89 | 533.60 | 3.54 |
| 2 | 7.74 h | 17.55 h | 222.37 | 1205.40 | 4.30 |
| 3 | 4.19 h | 20.11 h | 75.50 | 452.20 | 4.20 |

## Business Recommendations

1. **Reduce delayed deliveries** by focusing on the operational factors associated with the delayed group.
2. **Investigate Cluster 0**, which has relatively long delivery time, high delivery cost, and the lowest customer rating.
3. **Study Cluster 2** to understand why long-distance deliveries can still receive high customer ratings.
4. **Use predictive modeling** to estimate delivery time before dispatch.
5. **Monitor distance, vehicle type, weather, and delivery mode** as potential operational drivers.
6. **Improve customer experience** by identifying delivery segments with lower ratings.
7. **Use clustering for targeted logistics strategies** instead of applying the same approach to every delivery.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- Jupyter Notebook
- GitHub

## Repository Structure

```text
Logistics-Delivery-Analysis/
│
├── Logistics_Delivery_Analysis.ipynb
├── Logistics_Delivery_Final.csv
├── Logistics_Delivery_Analysis_Report.docx
└── README.md
```

## How to Run the Project

1. Download or clone this repository.
2. Open `Logistics_Delivery_Analysis.ipynb` in Google Colab or Jupyter Notebook.
3. Upload `Logistics_Delivery_Final.csv` if required.
4. Run the notebook cells from top to bottom.
5. Review the KPI, regression, clustering, and visualization outputs.

## Author

**Naveen Karangula**

This project was developed as a logistics data analytics and machine learning project demonstrating data cleaning, exploratory analysis, KPI analysis, predictive modeling, and clustering.
