Credit Card Customer Segmentation (Clustering)

📌 Project Overview

This project focuses on segmenting credit card holders based on their usage behavior and financial habits.
By analyzing a dataset of approximately 9,000 active credit card holders, we applied unsupervised machine learning 
(K-Means Clustering) to identify distinct customer personas.
These insights help banks and financial institutions design targeted marketing strategies and manage credit risk.

🛠️ Data Preprocessing & Engineering

inancial data is notoriously "messy" and highly skewed. 
This project utilizes an advanced cleaning pipeline to ensure robust clustering:

Data Cleaning: Removed logical inconsistencies (Tenure and Credit Limit $\le 0$).

Missing Value Imputation: Handled missing MINIMUM_PAYMENTS using Median Imputation to avoid outlier distortion.

Outlier Handling: Applied Clipping (Winsorization) at the 1st and 99th percentiles to neutralize extreme anomalies.

Skewness Correction:

Log1p Transformation: Applied to heavily right-skewed features like PURCHASES and CASH_ADVANCE.

Square Root Transformation: Used for moderately skewed frequency data.

Reflection + Log: Used to handle negative skewness in BALANCE_FREQUENCY.

Yeo-Johnson Power Transform: Applied to TENURE to normalize its distribution.

Feature Scaling: Utilized RobustScaler to ensure all features contribute equally to
                 distance calculations without being dominated by remaining outliers.


🤖 Modeling
Dimensionality Reduction: Applied PCA (Principal Component Analysis) to reduce data to 2 components for effective visualization of clusters.

K-Means Clustering:

Determined the optimal number of clusters using the Elbow Method and Silhouette Scores.

Selected K=3 as the optimal balance between granularity and business interpretability.

Cluster,Persona,Characteristics

Label 0,The Power Users,"High engagement across all metrics. High purchase frequency, larger transaction volumes, 
and consistent, high payments. Often has higher credit limits."

Label 1,The Casual Users,"Low overall activity. Occasional small purchases, lower payment amounts,
and generally lower credit limits. Represents ""emergency only"" or budget-conscious users."

🚀 Technologies Used
Python (Pandas, NumPy)

Scikit-Learn (KMeans, PCA, RobustScaler, SimpleImputer)

SciPy (Stats, Box-Cox)

Matplotlib & Seaborn (Data Visualization)

📂 Project Structure
Credit_card.ipynb: The complete end-to-end analysis notebook.

CC.csv: The raw dataset containing customer transactions and credit info.

README.md: Documentation of the project.
