# TourismBalance AI: DOSM Datathon 2026

![Status](https://img.shields.io/badge/Status-Completed-brightgreen) ![Tech](https://img.shields.io/badge/Tech-Power%20BI%20%7C%20Machine%20Learning%20%7C%20Analytics-blue) ![Data](https://img.shields.io/badge/Data-OpenDOSM%20%7C%20data.gov-orange)

An interactive intelligence dashboard predicting tourism-linked rail mobility demand across Malaysia. Built as the official submission for the **DOSM Datathon 2026** by Team *The Outliers*.

## Video Demo & Report
> **[?? Watch Video Demo](https://github.com/jefflaw0618-jpg/DOSM-Datathon-2026/blob/master/TheOutliers_Datathon2026_Video.mp4)** | **[View PDF Report](./TheOutliers_Datathon2026_Report.pdf)**

## Problem Statement
Balancing tourism demand with infrastructure capacity is a critical challenge. **TourismBalance AI** addresses this by combining state-level tourism intelligence with machine-learning-driven rail mobility forecasting. It provides actionable demand forecasts (Day 1 to Day 7), relative demand classifications, and smart lower-demand travel guidance for public commuters and stakeholders.

## Data Sourcing & Open Data
A core strength of this project is its reliance on official, high-quality public datasets. All data pipelines ingest directly from Malaysia's national open data portals:
* **[OpenDOSM](https://open.dosm.gov.my/):** Leveraging the Department of Statistics Malaysia's official repository for granular state-level tourism and demographic indicators.
* **[data.gov.my](https://data.gov.my/):** Utilizing national public sector datasets for high-frequency public transit (KTMB and Rapid Rail) mobility movements.

## Methodology & Machine Learning
The project bridges advanced predictive analytics with intuitive business intelligence:

* **Forecasting Pipeline:** Trained candidate models including **Weekly Baseline, Linear Regression, Random Forest, and XGBoost** to predict 15 tourism-linked transit targets.
* **Model Validation (Train/Val/Test):** Strict chronological splits to train candidates, select the best model during validation, and lock it for retrospective testing to prevent data leakage.
* **Evaluation Metrics:** Models were evaluated strictly on Mean Absolute Error (MAE), Root Mean Square Error (RMSE), and Weighted Absolute Percentage Error (WAPE).
* **Demand Classification:** Categorised forecasted traffic into *Normal* (< Q75), *Elevated* (Q75–Q90), and *Unusually High* (≥ Q90) to provide relative capacity context.

## Visualisation & Dashboarding (Power BI)
The analytical outputs were productionised into a robust **Microsoft Power BI** dashboard featuring 5 core pages:
1. **Executive Overview:** High-level tourism activity and model performance summaries.
2. **State Tourism Intelligence:** Geospatial comparisons and ranking of state-level tourism indicators.
3. **AI Mobility Demand Forecast:** Direct predictive windows with demand classes and source recency.
4. **Smart Travel Recommendation:** Forecast-derived guidance indicating optimal travel hours/days to avoid congestion.
5. **ML Performance & Evaluation:** Transparent, retrospective Actual vs. Predicted results and error metrics.

## Project Structure

```text
TheOutliers_Datathon2026_Dashboard.zip      # Contains the PowerBI (.pbix) and raw data
TheOutliers_Datathon2026_Report.pdf         # Comprehensive methodology and findings report
TheOutliers_Datathon2026_Video.mp4          # 10-minute presentation video
```

## Run Locally

### Prerequisites
* **Microsoft Power BI Desktop** (Version August 2026 or newer)
* Windows OS (Required for Power BI Desktop)

### Setup Instructions
1. Clone the repository and ensure you have Git LFS installed (due to large file sizes):
   ```bash
   git clone https://github.com/jefflaw0618-jpg/DOSM-Datathon-2026.git
   ```
2. Unzip `TheOutliers_Datathon2026_Dashboard.zip`.
3. Open `TheOutliers_Datathon2026_Dashboard.pbix` in Power BI Desktop.
4. Interact with the slicers, filters, and page tabs to explore the demand forecasts.

## Limitations and Future Improvements
* **Proxy Limitations:** Rail passenger movements are used as a proxy for mobility, not direct tourist arrival counts.
* **External Variables:** The current predictive model does not account for sudden external shocks (e.g., weather anomalies, dynamic public holidays, or spontaneous events).
* **Granularity Mismatch:** KTMB data is evaluated hourly, while Rapid Rail data relies on daily aggregates. Future iterations will seek to standardise temporal granularity.
