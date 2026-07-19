# 🛒 SmartCart Segmentation System

Unsupervised ML system that segments e-commerce customers into behavior-based clusters (K-Means, PCA) to enable targeted marketing and churn prevention.

# 📌 Problem Statement

SmartCart is a growing e-commerce platform serving customers across multiple countries. The company has collected extensive customer data — 2,240 customer records across 22 attributes covering demographics, purchase behavior, website activity, and campaign responses.

Currently, SmartCart applies generic marketing strategies to all customers, regardless of their actual behavior. This leads to:


Inefficient marketing spend
Missed opportunities to retain high-value customers
Delayed identification of churn-prone users


Goal: Build an intelligent customer segmentation system using unsupervised machine learning to group customers into meaningful clusters based on purchasing behavior, engagement, and loyalty — enabling data-driven, personalized marketing and retention strategies.


# 📊 Dataset Overview

Each row represents a customer, described across four feature groups:
Demographics: Year_Birth, Education, Marital_Status, Income, Kidhome, Teenhome, Dt_Customer
Spending Behaviour: MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts, MntGoldProds
Purchase Frequency: NumDealsPurchases, NumWebPurchases, NumCatalogPurchases, NumStorePurchases, NumWebVisitsMonth
Feedback / Engagement: Recency, Complain

# ⚙️ Approach

Raw Data → Data Preprocessing → Feature Engineering → Outlier Detection & Removal →
Correlation Analysis → Encoding → Scaling → PCA (2D / 3D) →
Clustering (K-Means, Agglomerative) → Cluster Characterization → Cluster Summary


## Data Preprocessing — handled missing values in the dataset
Feature Engineering — engineered new, business-relevant features from raw columns:

Age (from Year_Birth)
Customer_Tenure (days since enrollment, from Dt_Customer)
Total_Spending (sum of all Mnt* product categories)
Total_Children (combined Kidhome + Teenhome)
Simplified/classified Education into broader qualification tiers
Classified Marital_Status into simplified living status categories
Dropped redundant/unnecessary columns post feature engineering



Outlier Detection & Removal — identified and removed outliers to prevent skewed cluster formation
Correlation Analysis — examined feature correlations to extract early insights and check for multicollinearity
Encoding — applied One-Hot Encoding to categorical features
Scaling — standardized all numerical features using StandardScaler
Dimensionality Reduction (PCA) — reduced feature space to 2D and 3D for visualization and clustering efficiency
Clustering — applied and compared K-Means and Agglomerative (Hierarchical) Clustering
Cluster Characterization — analyzed how every feature behaves across clusters to understand each segment's identity
Cluster Summary — synthesized findings into clear, business-friendly customer segment profiles
