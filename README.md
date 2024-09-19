# Supervised and Unsupervised Learning Applied on Trending Youtube Videos Statistics Dataset
## Purpose of the Project
The supervised learning model is used for predicting the engagement rate and classification of videos as high or low engagement.  
Why is the model predicting engagement?  
•	Engagement is a key factor in determining a video's performance beyond just views. High engagement often indicates that viewers are interacting with the content, which could lead to better recommendations by platforms like YouTube.  
•	Platforms like YouTube reward videos based on engagement metrics (e.g., likes, shares, comments), and not just views. Highly engaged viewers are more likely to watch ads, contribute to higher ad revenue, and attract sponsors. Therefore, high engagement associates with potential revenue.  

In the unsupervised learning part, the model is grouping (clustering) videos based on their similarities without predicting any labels like "high engagement".

## Implementation
When implying supervised learning to dataset, logistic regression algorithm is used to predict whether a video has high engagement or not based on the engagement score. The engagement score is calculated as sum of likes and comments divided by views, which is choosen arbitrarly for this project. In summary, the model is classifying videos as high engagement or not based on the numbers of likes, dislikes, comments and whether the comments and ratings are disabled or not.
For optimization of hyperparameters, the Randomized Search algorithm is choosen since it worked better than the Grid Search for this dataset.  

The unsupervised clustering model includes K-Means Clustering algorithm. The model assign videon on clusters based on some common characteristics without knowing ahead of time whether they have high engagement or not.

## About The Dataset: Trending YouTube Video Statistics
This dataset includes several months of data on daily trending YouTube videos. Data is included for the US, GB, DE, CA, FR, RU, MX, KR, JP and IN regions (USA, Great Britain, Germany, Canada, France, Russia, Mexico, South Korea, Japan and India respectively), with up to 200 listed trending videos per day. This dataset is a daily record of the top trending YouTube videos published from 07.23.2006 to 06.14.2018.  
The randomly selected 30000 rows of the data from US region is used for this project.

## Results
Supervised Learning:  
Before Hyperparameter Optimization, the accuracy score was 96.25% but precision, recall and F1 scores was very low, indicating that the model struggles to detect high engagement videos, likely due to class imbalance.  
After Hyperparameter Optimization, there is a slight improvement in accuracy, precision and recall scores but class imbalance remains a challenge for the model.  

Unsupervised Learning:  
The Silhouette Score of 0.792 and Inertia show that the clusters are well-defined, compact and well-formed within themselves.
The Davies-Bouldin Index of 0.749 suggests there is moderate separation between the clusters.  
The low values of ARI, Homogeneity, Completeness, and V-Measure indicate that the clusters do not strongly reflect any underlying true categories (which may be expected in purely unsupervised tasks).  
This means the K-Means model finds meaningful clusters, though they don't align perfectly to predefined labels (such as "high engagement").   

Here is the link for Kaggle notebook: : https://www.kaggle.com/code/cigdemyasar/aygazml-trending-youtube
