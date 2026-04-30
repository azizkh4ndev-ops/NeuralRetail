## Week 1 – Data Engineering & Feature Development

### Data Preprocessing
- Removed cancelled transactions (InvoiceNo starting with 'C')
- Filtered invalid records (Quantity > 0, UnitPrice > 0)
- Dropped missing CustomerID values
- Final dataset cleaned and standardized for downstream modeling

### Exploratory Data Analysis (EDA)
- Identified skewness in Monetary distribution (heavy outliers)
- Observed strong seasonality patterns in transaction data
- Detected customer purchase frequency imbalance
- Generated visual insights for revenue distribution and customer activity

### Feature Engineering
- Built **RFM features**:
  - Recency: Days since last purchase
  - Frequency: Number of transactions
  - Monetary: Total spend per customer
- Created **time-series features**:
  - Daily aggregated sales
  - Rolling averages (7, 14, 30 days)
  - Lag features (t-1, t-7, t-14)

### Outputs
- `data/processed/cleaned_data.csv`
- `data/processed/rfm.csv`
- `data/processed/time_series.csv`



## Week 2 – Customer Segmentation

### Approach
- Applied **log transformation** to reduce skewness in RFM features
- Standardized features using `StandardScaler`
- Performed clustering using **KMeans algorithm**

### Model Selection
- Used **Elbow Method** for initial cluster estimation
- Finalized cluster count using **Silhouette Score optimization**

### Results
- Identified **4 distinct customer segments**:
  - High Value Customers (high frequency, high spend, recent activity)
  - Regular Customers (moderate engagement)
  - At-Risk High Value Customers (high spend but inactive)
  - Low Value / Lost Customers (low engagement and spend)

### Business Impact
- Enables targeted marketing and retention strategies
- Identifies high-risk churn segments for intervention
- Supports personalized campaign design

### Visualizations
- Customer segmentation scatter plot (Recency vs Monetary)
- Cluster distribution (customers per segment)
- Heatmap of cluster characteristics

### Outputs
- `data/processed/rfm_segmented.csv`
- Cluster visualizations in `outputs/plots/`



## Dataset
Due to size constraints, the raw dataset is not included in the repository.

Recommended sources:
- UCI Online Retail Dataset
- Kaggle Retail datasets

Processed datasets used in this project are available under `data/processed/`.


