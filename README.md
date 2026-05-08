# NCR Ride Bookings: Exploratory Data Analysis and Interactive Dashboard

## Project Overview
This project presents a comprehensive end-to-end data analysis pipeline for a ride-sharing dataset containing 150,000 booking records within the National Capital Region (NCR). The objective is to identify operational bottlenecks, analyze consumer behavior, and visualize spatial-temporal demand using high-dimensional interactive visualizations.

## Key Performance Indicators (KPIs)
Based on the final processed dataset, the following metrics were established:
*   Total Bookings: 150,000
*   Successful Completions: 93,000
*   Gross Revenue: ₹70.1M
*   Average Customer Satisfaction: 4.32/5.0
*   Overall Cancellation Rate: 25.0%
*   Average Trip Distance: 26.0 km

## Data Pipeline and Preprocessing
The analysis involved rigorous data cleaning and feature engineering to ensure statistical reliability:

### 1. Data Cleaning and Imputation
*   **String Sanitization:** Cleaned ID columns ('Booking ID', 'Customer ID') by removing special characters and whitespace.
*   **Missing Value Strategy:** Used conditional median imputation for numeric features (Avg VTAT, Avg CTAT, Ratings) based on the "Completed" ride status to prevent data leakage from cancelled trips.
*   **Outlier Management:** Implemented the Interquartile Range (IQR) method to clip extreme values in 'Booking Value' and 'Ride Distance', ensuring that visualizations and averages are not skewed by anomalies.

### 2. Feature Engineering
*   **Temporal Features:** Extracted Hour, Day of Week, Month, and Weekend indicators from timestamps.
*   **Revenue Metrics:** Calculated 'Revenue per km' to assess the profitability of different vehicle classes.
*   **Performance Scoring:** Created a 'Satisfaction Score' by aggregating Driver and Customer ratings.
*   **Categorization:** Segmented Vehicle Types into broader classes (Two-Wheeler, Sedan, Budget, XL) and categorized Vehicle Arrival Time (VTAT).

## Analytical Modules

### Exploratory Data Analysis (EDA)
*   **Distribution Analysis:** Utilized Box and Violin plots to analyze the spread of booking values and distances across different ride statuses.
*   **Correlation Matrix:** Generated a heatmap to identify relationships between pricing, distance, and wait times.

### Temporal and 3D Analytics
*   **Demand Heatmaps:** Visualized booking density by hour and day of the week.
*   **3D Surface Plots:** Analyzed hourly booking trends across different days to identify peak demand windows.
*   **Multidimensional Scaling:** Used 3D scatter plots to visualize the intersection of revenue, distance, and satisfaction scores.

### Geospatial Intelligence (Mapbox Integration)
*   **Route Optimization:** Visualized the top 20 busiest routes using flow-line maps where line thickness represents ride volume.
*   **Location Analysis:** Implemented density maps to identify high-demand pickup and drop-off zones.
*   **Cancellation Risk Mapping:** Mapped zones with high "No Driver Found" or customer cancellation rates to identify service gaps.

## Technical Stack
*   **Language:** Python
*   **Data Manipulation:** Pandas, NumPy
*   **Visualization:** Plotly (Express and Graph Objects)
*   **Environment:** Google Colab / Jupyter
*   **Geospatial Processing:** Mapbox API
