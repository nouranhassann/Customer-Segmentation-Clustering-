# Customer-Segmentation-Clustering
# Customer Segmentation & Behavior Analysis

## Project Overview
This project analyzes **customer purchasing behavior** using transaction data to identify distinct customer segments. The goal is to optimize marketing strategies, improve retention, and target high-value customers.

**Dataset:** 541,909 transactions with features like InvoiceNo, StockCode, Quantity, UnitPrice, CustomerID, and InvoiceDate.

## Workflow

### 1. Data Cleaning & Preparation
- Dropped missing CustomerIDs, negative quantities, and zero or negative prices.  
- Removed duplicates → final dataset: **392,692 records**.  
- Converted `InvoiceDate` to datetime and created snapshot date for Recency calculation.

### 2. Feature Engineering – RFM Analysis
- **Recency:** Days since last purchase  
- **Frequency:** Number of unique invoices per customer  
- **Monetary:** Total spending per customer  
- Handled outliers by clipping extreme values (1st and 99th percentiles).  

### 3. Scaling & Dimensionality Reduction
- Standardized features with `StandardScaler`.  
- Applied PCA to reduce dimensions and visualize clusters (captured 90% variance).

### 4. Clustering
- **KMeans:** Tested K=2 to 8 → best Silhouette = 0.66 at K=2  
- **DBSCAN:** Explored eps and min_samples → final model: eps=0.5, min_samples=10  
  - **Number of clusters:** 2  
  - **Noise ratio:** 2.79%  
  - **Silhouette score:** 0.814 → strong cluster separation  

### 5. Cluster Profiling
| Cluster | Description |
|---------|-------------|
| 0       | High frequency & high monetary → VIP customers |
| 1       | Low frequency & high recency → Inactive customers |
| -1      | Noise → irregular/rare buyers |

### 6. Insights
- DBSCAN provided better segmentation than KMeans (higher Silhouette Score).  
- Identified high-value and inactive customers for targeted marketing.  
- PCA visualization confirms clear separation of clusters.  

## Tools & Technologies
- Python, Pandas, NumPy  
- Scikit-learn (KMeans, DBSCAN, PCA)  
- Matplotlib, Seaborn  
- Feature Engineering (RFM Analysis)  

## Visualizations
- Log(Monetary) distribution  
- PCA 2D cluster scatter plot  
- Cluster profiles and summary statistics
## Contributors
- Nouran Hassan
- [Bassmala Mahmoud](https://github.com/bassmalamahmoud)
- [Mohamed (mu20042006-cyber)](https://github.com/mu20042006-cyber)
- [Naiera Kassem](https://github.com/naierakassem614-tech)
- Nada Eissa
  

This project was developed collaboratively as a team effort. All contributors participated equally in data preparation, analysis, modeling, and documentation.
 

