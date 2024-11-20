# Machine Learning Project

## Team : Alpha (07)
202418005 Anandita Saolapurkar</br>
202418015 Deepanshi Acharya</br>
202418043 Chandan Pandit
</br>

## Project Overview
This project aims to perform unsupervised learning to **cluster countries** based on various **socio-economic indicators** such as GDP, inflation, life expectancy, and literacy rate. The dataset used for this project was sourced from the World Bank API, containing key indicators for all countries.

### Dataset
The data was sourced from the World Bank API. Indicators used include:
1. **Country**: The name of the country.
2. **child_mort**: Death rate of children under 5 years of age, per 1,000 live births.
3. **exports**: Exports of goods and services per capita, given as a percentage of GDP per capita.
4. **health**: Total health expenditure per capita, expressed as a percentage of GDP per capita.
5. **imports**: Imports of goods and services per capita, given as a percentage of GDP per capita.
6. **income**: Net income per person.
7. **inflation**: The annual growth rate of total GDP, measured as a percentage.
8. **life_expectancy**: The average number of years a newborn is expected to live, assuming current mortality patterns.
9. **total_fer**: The number of children born to a woman, based on current age-fertility rates.
10. **gdpp**: GDP per capita, calculated as the total GDP divided by the total population.
11. **literacy_rate**: The percentage of the population aged 15 and above that can read and write.

#### Dataset Source
[World Bank API Dataset](https://www.kaggle.com/code/gcmadhan/unsupervised-learning-countries-need-finance)
</br></br>

## Key Phases of the Project

1. **Data Preprocessing**:
   - **KNN Imputation** was used to handle missing data by filling in missing values based on the most similar countries (neighbors).
   - **Scaling**: The numeric data was standardized using `StandardScaler` to ensure that the clustering algorithms perform optimally.

2. **Dimensionality Reduction**:
   - **PCA (Principal Component Analysis)** was used to reduce the dimensionality of the dataset while preserving 95% of the variance. This helped in visualizing the data in lower dimensions and identifying meaningful clusters.

3. **Clustering**:
   - **KMeans Clustering**: After experimenting with various cluster numbers, we selected 3 clusters as the optimal number based on the Elbow Method and silhouette scores.
   - **DBSCAN**: A density-based method, but it didn't yield clear clusters in this case.
   - **Hierarchical Clustering**: Generated clusters, but the Calinski-Harabasz score was lower than that for KMeans, suggesting less well-defined clusters.

### Key Metrics:
- **Calinski-Harabasz Score (KMeans)**: 192.7133
- **Calinski-Harabasz Score (Hierarchical)**: 106.503
- **Silhouette Score**: Best for 5 clusters (compared visually with KMeans' 3 clusters)
</br></br>

## Practical Applications
This clustering approach can be applied in several real-world contexts:

1. **International Policy Making**: Policymakers can identify countries with similar socio-economic backgrounds and design targeted interventions.
2. **Resource Allocation**: International organizations can allocate resources such as development aid based on the clusters.
3. **Market Segmentation**: For businesses operating internationally, understanding socio-economic clusters can inform market entry and pricing strategies.
</br></br>

## Conclusion
The project successfully demonstrated how unsupervised learning can be used to group countries based on their socio-economic characteristics. By applying KMeans clustering, we identified three distinct clusters that provide valuable insights into countries’ socio-economic backgrounds. The model's performance was evaluated using the **Calinski-Harabasz score**, which indicated that KMeans performed better than hierarchical clustering in this case.

The following table summarizes the predicted clusters and their corresponding socio-economic profiles:

| Cluster ID | Countries in the Cluster | Socio-Economic Profile |
|------------|--------------------------|------------------------|
| 1          | Countries with high GDP and life expectancy | High Socioeconomic |
| 2          | Countries with medium GDP and moderate life expectancy | Middle Socioeconomic |
| 3          | Countries with low GDP and lower life expectancy | Low Socioeconomic |

</br>
