# Evaluation-of-physiological-and-behavioral-patterns-of-EAS-users-using-k-means
# Evaluation of Physiological and Behavioral Patterns of EAS Users Using Unsupervised Machine Learning Predictive Models

## Project Overview

This project explores the potential to identify physiological and behavioral patterns that distinguish users of anabolic steroids (EAS) from non-users within a population, utilizing unsupervised machine learning techniques, specifically K-Means clustering. Due to the absence of a proprietary dataset on this specific topic, a synthetic dataset was generated based on consolidated findings from scientific literature, aiming to reflect real-world relationships and values observed in studies on the physiological and behavioral effects of anabolic steroid use.

The primary goal is to demonstrate that unsupervised methods can reveal inherent structures in the data that correlate strongly with steroid use status, even without explicit labeling during the clustering process.

## Dataset

The dataset used in this project is synthetic, created by synthesizing information from various consolidated articles and meta-analyses in the scientific literature concerning the physiological and behavioral impacts of anabolic steroid use. It contains features such as age, sex, heart rate, blood pressure (systolic and diastolic), lean mass index, body fat percentage, BMI, cholesterol levels, testosterone levels, and a binary indicator for steroid use (`steroid_use`).

## Methodology: K-Means Clustering

The K-Means algorithm was chosen for this project due to its suitability for identifying distinct groups within numerical data in an unsupervised manner. The steps involved were:

1.  **Data Loading and Validation:** The synthetic dataset was loaded and subjected to validation checks, including verifying for duplicates, handling whitespace, checking for empty cells, and examining unique values and data types.
2.  **Data Preprocessing:** Numerical features were selected, and the 'id' column was removed as it is not a relevant feature for clustering. The data was then scaled using `StandardScaler` to ensure that all features contribute equally to the distance calculations in K-Means.
3.  **Determining the Number of Clusters (Elbow Method):** The Elbow Method was applied by calculating the inertia for a range of cluster numbers (k=1 to 10). The resulting elbow plot provided visual guidance on the optimal number of clusters. Based on the plot and the project's objective of exploring potential sub-patterns within user and non-user groups, K=4 was selected for the final clustering.
4.  **Applying K-Means:** The K-Means algorithm was applied to the scaled data with 4 clusters. The cluster labels assigned by the algorithm were then added back to the original DataFrame.

## Analysis and Results

The analysis of the clustering results with K=4 revealed a strong and significant pattern related to steroid use:

*   **Clusters 0 and 3:** These clusters predominantly grouped individuals who **do not use anabolic steroids**.
*   **Clusters 1 and 2:** These clusters predominantly grouped individuals who **use anabolic steroids**.

This clear separation, achieved through an unsupervised approach, demonstrates that the physiological and behavioral features in the dataset contain substantial information for distinguishing steroid users from non-users. The presence of two non-user clusters and two user clusters suggests potential sub-patterns within these populations.

Further analysis of the mean characteristics within each cluster (as shown in the output of cell `1ed02759`) allowed for the characterization of these groups:

*   Comparison of mean values across clusters highlights key discriminatory features such as `testosterone_level`, `lean_mass_index`, `body_fat`, and `cholesterol`, which show significant differences between user and non-user clusters.
*   Differences in mean values between Cluster 0 and 3 (non-users) and Cluster 1 and 2 (users) suggest the existence of distinct profiles within these broader categories, potentially related to variations in physiological responses or usage patterns.

The PCA visualization (generated in cell `77aa71f2`) visually confirms this separation, showing distinct groupings of the user and non-user clusters in the reduced-dimensional space, driven by the principal components that capture the most significant variance in the data, influenced by the key discriminatory features.

## Conclusion

The unsupervised K-Means clustering, combined with the analysis of steroid use distribution, cluster characteristics, and PCA visualization, strongly indicates that the physiological and behavioral features in this synthetic dataset contain clear patterns that differentiate anabolic steroid users from non-users. The analysis successfully identified clusters that align closely with steroid use status and highlighted the key physiological and behavioral variables most influential in this distinction. The presence of sub-clusters within user and non-user groups suggests the potential for identifying more granular profiles based on these features. This project demonstrates the effectiveness of unsupervised machine learning in revealing meaningful patterns in biological and behavioral data.

## How to Run the Notebook

1.  Clone this repository to your local machine.
2.  Open the notebook in Google Colab or a compatible Jupyter environment.
3.  Ensure you have access to the dataset file (`dataset_fisiologico_EAS_2000.csv`) and update the file path in the data loading cell if necessary.
4.  Run the cells sequentially to execute the data loading, validation, preprocessing, clustering, analysis, and visualization steps.
