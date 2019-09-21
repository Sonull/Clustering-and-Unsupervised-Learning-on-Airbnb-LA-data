# Information about the Analysis

* The analysis has been done on Airbnb dataset for Los Angeles, California - United States of America
* The dataset contains information on 22,453 rooms
* Total number of variables = 29
* Source of data : www.kaggle.com
* For the purpose of the analysis, the words ‘rooms’/‘room’ mean ‘airbnb rooms’/’airbnb’ (which is an international convention)
* All occurrences of the word ‘bedrooms’ strictly mean bedrooms and should not be confused with the ‘rooms/room’ mentioned in the point above

# Objective of the Analysis
There were two objectives:
  * Create clusters of similar Airbnb rooms in Los Angeles, California
  * Build a multivariate linear regression model to predict the price of a room in each cluster
 
# Overview of the steps involved
* Identification of dependent and independent variables
* Variable reduction – dropping variables that would not be used for the analysis
* Missing value treatment
  * For numerical variables, missing values were replaced by the mean of the variable
  * For character variables, missing values were replaced by a new categorical value “undefined”
* Feature Engineering
  * Created 3 new independent variables that were used for clustering as well as for model building
* Clustering using k means
  * 4 clusters were created after multiple iterations
* Data Visualization
* Multivariate Linear Regression Analysis
  * One multivariate linear regression model was then built for each cluster (only the final models with significant variables have been shared)

# Dependent Variable

* The variable ‘log_price’ which is the log of price of each room is the dependent variable

# Independent Variables for Clustering and Model Building

![varsdesc](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/varsdesc.png)


# Data Preparation

![dataprep1_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/dataprep1_new.png)

![dataprep2_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/dataprep2_new.png)

# Clustering

![clustering1_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/clustering1_new.png)

![Elbow_Curve_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/Elbow_Curve_aug30.png)

![clustering2_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/clustering2_new.png)

![clustersize](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/clustersize.png)

![clustering3_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/clustering3_new.png)

# Visualization of the data

![v1](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v1.png)

![v2](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v2.png)

![Chart1_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/Chart1_aug30.png)

![v3](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v3.png)

![chart2_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart2_aug30.png)

![v4](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v4.png)

![chart3_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart3_aug30.png)

![v5](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v5.png)

![chart4_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart4_aug30.png)

![v6](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v6.png)

![chart6_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart6_aug30.png)

![chart5_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart5_new.png)

# Multivariate Linear Regression Analysis
# Cluster 1
# Cluster 2
# Cluster 3
# Cluster 4

