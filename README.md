# undp-climate-vote-2024-eda-and-clustering-analysis
Analysis of a survey done by UNDP in 2024 on global attitudes towards climate change. The analysis covers EDA and unsupervised machine learning techniques to understand the characteristics of the data such as k-means and hierarchical clustering.

# Project Overview
This project performs an in-depth analysis of the [UNDP People's Climate Vote 2024](https://peoplesclimate.vote/data-center), the largest standalone public opinion survey on climate change. Using unsupervised machine learning and exploratory data analysis (EDA), this repository uncovers distinct patterns in global climate attitudes, identifying how different countries and demographics perceive climate action, corporate responsibility, and the transition to renewable energy.

# Repository Structure
* `peoples-climate-vote-eda-github.ipynb`: Exploratory data analysis focusing on demographic breakdowns, specifically analyzing the "generation gap" in support for renewable energy transitions across different nations.
* `peoples-climate-vote-database-clustering-kmeans-hierarchical-github.ipynb`: The main machine learning workflow. It preprocesses survey data, reduces dimensionality using PCA, and segments countries into distinct clusters using K-Means and Hierarchical clustering.

# Methodology

## 1. Data Preprocessing & Feature Engineering
* **Data Source:** UNDP People's Climate Vote 2024 Database.
* **Feature Construction:** Created composite features by combining `Question Text` + `Response` to pivot the dataset into a format suitable for country-level analysis (Rows: Countries, Columns: Weighted Mean of Responses).
* **Standardization:** Applied `StandardScaler` to normalize response percentages across 75+ unique survey questions.

## 2. Unsupervised Learning (Clustering)
To group countries with similar climate sentiment profiles, I implemented:
* **K-Means Clustering:** Determined the optimal number of clusters ($k=3$).
* **Hierarchical Clustering:** Used to validate K-Means results.
* **PCA (Principal Component Analysis):** Reduced the high-dimensional feature space to 2 components for 2D visualization of country clusters.

## 3. Exploratory Data Analysis (EDA)
* **Demographic Focus:** Analyzed age-based disparities in climate sentiment.
* **Key Question:** "How quickly should your country replace coal, oil, and gas with renewable energy?"
* **Visualizations:** Generated bar charts and heatmaps to visualize the urgency of support for renewables among different age groups (18-35, 36-59, 60+).

# Key Findings
* **Global Clusters:** The analysis successfully segmented 70+ countries into **3 distinct clusters**. These clusters likely represent groups of nations with:
    * *Cluster A:* High urgency/High anxiety regarding climate change.
    * *Cluster B:* Moderate concern/Mixed views on corporate performance.
    * *Cluster C:* Least concerned/happy with status quo.
    *(Note: See the notebook visualizations for the specific country breakdowns per cluster).*
* **Regional Alignment:** The PCA visualization revealed that while some clusters align with geographical regions (e.g., Europe, Americas), climate sentiment often transcends borders, grouping countries by economic or vulnerability status rather than just location.
* **Consensus on Collaboration:** Preliminary EDA suggests a high global consensus (often >80%) on countries working together on climate change despite other disagreements.

# Technologies Used
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `sklearn` (KMeans, PCA, StandardScaler, Silhouette Score)
* **Visualization:** `seaborn`, `matplotlib`

# License
This project is open-source and available for educational and research purposes. Data is sourced from the UNDP.
