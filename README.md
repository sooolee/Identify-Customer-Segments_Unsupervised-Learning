# Identify Customer Segment

In this project, I apply ***unsupervised learning techniques*** to identify segments of the population that form the core customer base for a mail-order sales company in Germany. 

> Data is given in csv format. 
> - Demographics data for the general population: Dataset based on which the model is developed.
> - Demographics data for customers of a mail-order company: Dataset to which the model is applied.
>> Note: The datasets are not shared in GitHub due to the license term. 



## Data Preprocessing Steps
- Convert Missing Value Codes to NaNs
- Assess Missing Data in Each Column and Each Row & Delete Some Data Accordingly
- Feature Selection, Re-encode Categorical Features & Engineer Mixed-Type Features
- Feature Transformation: Feature Scaling, Dimentionality Reduction using PCA (Principal Components Analysis), and Interprete Principal Components

## Clustering Process
- Apply `k-means` clustering to the General Population dataset and use the average within-cluster distances from each point to their assigned cluster's centroid to decide on a number of clusters to keep.

<img src="https://github.com/sooolee/Identify-Customer-Segments_Unsupervised-Learning/blob/main/images/num_cluster.png?raw=true" width="400">
- Once the final number of clusters is decided, re-fit the model (My choice is 20).
- Carry the same data preprocessing for the Customer dataset.
- Apply the model to the Customer dataset: "Predict"

## Compare Customer Data to Demographics Data
- Compute the proportion of data points in each cluster for the general population and the customer data. 

<img src="https://github.com/sooolee/Identify-Customer-Segments_Unsupervised-Learning/blob/main/images/gen-to-cust.png?raw=true" width="600">

- Identify most overrepresented and underrepresented customer clusters compared to general population.
- Use the `.inverse_transform()` method of the PCA to transform centroids back to the original data space to find important features to these clusters.
- Interprete what kinds of people are typified by these clusters. 