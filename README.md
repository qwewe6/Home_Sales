
# Home_Sales
Module 22 Homework

## Home Sales Analysis with PySpark

### Overview

This project analyzes home sales data using PySpark to identify pricing trends. Key tasks include running SQL queries, caching tables, and optimizing performance with Parquet partitioning. The dataset was loaded from AWS S3 and processed using PySpark SQL.

### Tools & Technologies

- PySpark: Distributed data processing and SQL
- Python: Scripting and data analysis
- AWS S3: Source data storage
- GitHub: Version control

### Dataset Overview

`home_sales_revised.csv` includes:

- `id`: Sale ID
- `date`: Sale date
- `date_built`: Year built
- `price`: Sale price
- `bedrooms`, `bathrooms`, `floors`
- `sqft_living`, `sqft_lot`
- `waterfront`: 1 = Yes, 0 = No
- `view`: View score (0–100)

### Key Analyses

1. Avg. price of 4-bedroom homes by year
2. Avg. price of 3-bed, 3-bath homes by year built
3. Avg. price of large 2-floor 3/3 homes (≥ 2000 sqft) by year built
4. Avg. price by view rating (where avg ≥ $350K)
5. Query performance: uncached vs. cached
6. Parquet partitioning by `date_built` and performance comparison

### Highlights

- Created temp views for SQL access
- Cached tables to boost performance
- Partitioned data on `date_built`
- Compared query runtimes across uncached, cached, and partitioned setups

### Results Summary

| Query Description                        | Uncached Runtime     | Cached Runtime       | Partitioned Parquet Runtime |
|------------------------------------------|----------------------|----------------------|-----------------------------|
| Avg. Price per View Rating (≥ $350K)     | 0.1648 sec           | 0.3188 sec           | 0.2599 sec                  |

### How to Run

1. Clone the repo
2. Open `home_sales_main.ipynb` in Jupyter
3. Run all cells to complete the analysis
