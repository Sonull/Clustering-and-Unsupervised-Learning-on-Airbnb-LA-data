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


![clustering2_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/clustering2_new.png)

![Elbow_Curve_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/Elbow_Curve_aug30.png)

* The Elbow Curve showed that after 6 there is a decline in the calculated sum of squared errors (SSE)
* I ran one iteration with 6 and 5 number of clusters each but in both cases 1 or 2 clusters were really small so it made sense to decrease the number of clusters
* Moreover, the elbow curve shows that there is a very negligible increase after 4 number of clusters which can be  considered insignificant.Therefore, I built 4 mutually exclusive and exhaustive clusters using k-means
* In all, 200 variables were considered for clustering



![clustersize](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/clustersize.png)

* Cluster 3 is the biggest cluster with 75% of the rooms in it
* Cluster 1 is the smallest with just 1% of the rooms

![clustering3_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/clustering3_new.png)

# Visualization of the data

![v1](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v1.png)

# Chart 1

![v2](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v2.png)

![Chart1_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/Chart1_aug30.png)

* Cluster 3 has the highest number of ‘Entire home/apt’ as compared to all the other clusters followed by cluster 4
* The majority of ‘Private rooms’ are in cluster 3 
* Cluster 1 has no shared rooms
* Overall, there are more number of rooms of type ‘Entire home/apt’ followed by ‘Private rooms’ 

# Chart 2

![v3](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v3.png)

![chart2_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart2_aug30.png)

* The number of rooms with moderate cancellation policy is more than the number of rooms with flexible cancellation policy for each of the clusters 1, 2 and 4 but a completely opposite trend is observed in cluster 3 
* Overall, there were almost no rooms which had a super strict cancellation policy of 30 or even 60 days

# Chart 3

![v4](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v4.png)

![chart3_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart3_aug30.png)

* More than 10,000 rooms in cluster 3 were not instantly bookable
* In each cluster, there are more number of rooms that cannot be booked instantly than the rooms that can be booked instantly
* This difference is least in cluster 1 followed by cluster 2 but this could also be due to the sheer size of these two clusters

# Chart 4

![v5](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v5.png)

![chart4_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart4_aug30.png)

* Around 75% of the rooms in Cluster 3 have a cleaning fees associated with them while for cluster 2 and 4 around 85% of the rooms have a cleaning fees associated with them respectively
* Thus, more percentage of rooms in cluster 2 and 4 have a cleaning fees associated with them respectively than cluster 3 even when cluster 3 has more number of rooms

# Chart 5

![v6](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/v6.png)

![chart6_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart6_aug30.png)

* As the number of bedrooms increase, the log_price tends to increase. That is, there seems to exist a positive linear relationship between number of bedrooms and the log_price of the room
* The range of log_price for a place with 3 bedrooms is more in cluster 3 followed by cluster 4 while it is the smallest in cluster 1
* For a place with 4 bedrooms, the range of log_price in cluster 4 is almost equal to the range of log_price in cluster 3
* There are no rooms in cluster 1 with more than 3 bedrooms
* The maximum number of bedrooms that a room can have is 10 which is present in cluster 3

# Chart 6

![chart6_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/chart6_new.png)

![chart5_aug30](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/chart5_aug30.png)

* The log_price of the rooms follows a normal distribution 
* Interestingly, the average log_price of a room in each cluster is around $4.5
* The cheapest room in cluster 3 costs even less than the cheapest room in all the other clusters
* The most expensive room lies in cluster 3
* Overall, rooms in cluster 3 are the most expensive, followed by rooms in cluster 4 and 2
* The log_price of rooms in cluster 3 has the highest variance while the log_price of rooms in cluster 1 has the smallest variance


# Multivariate Linear Regression Analysis

# Cluster 1

![model1](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/model1.png)

![cluster1_model2](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/cluster1_model2.png)

# Conclusion

* Thus, the equation of multiple linear regression model for cluster 1 is:
# LogPrice of the room = 4.46011 + 0.11484 * accommodates - 0.11623 * bathrooms + 0.11663 * bedrooms – 0.11219 * privacy

* An increase in number of persons that the room can accommodate by 1 person will increase the log price of the room by $0.11484 when all other variables are held constant
* An increase in the number of bathrooms in the room by 1 bathroom will decrease the logprice of the room by $0.11623 when all other variables are held constant
* An increase in the number of bedrooms in the room by 1 bedroom will increase the logprice of the room by $0.11663 when all other variables are held constant
* An increase in the privacy index by 1 unit will decrease the logprice of the room by $0.11219 when all other variables are held constant


# Cluster 2

![model2_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/model2_new.png)

![cluster2_model2](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/cluster2_model2.png)

# Conclusion

* Thus, the equation of multiple linear regression model for cluster 2 is:
# LogPrice of the room = 3.81457 + 0.21501 * bathrooms + 0.13755 * bedrooms + 0.08836 * beds + 0.01223 * num_amenities + 
0.08371 * bathroom_luxury -0.15133* privacy

* An increase in number of bathrooms in the room by 1 bathroom will increase the logprice of the room by $0.21501 when all other variables are held constant
* An increase in in number of bedrooms in the room by 1 bedroom will increase the logprice of the room by $0.13755 when all other variables are held constant
* An increase in in number of beds in the room by 1 bed will increase the logprice of the room by $0.08836 when all other variables are held constant
* An increase in in number of amenities in the room by 1 amenity will increase the logprice of the room by $0.01223 when all other variables are held constant
* An increase in the bathroom_luxury index by 1 unit will increase the logprice of the room by $0.08371 when all other variables are held constant
* An increase in the privacy index by 1 unit will decrease the logprice of the room by $0.15133 when all other variables are held constant

# Cluster 3

![model3_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/model3_new.png)

![cluster3_model1](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/cluster3_model1.png)

# Conclusion
* Thus, the equation of multiple linear regression model for cluster 3 is:
# LogPrice of the room = 3.7762481 + 0.0827482 * accommodates + 0.1859950 * bathrooms + 0.1949640 * bedrooms + 0.0232852 * beds + 0.0099534 * num_amenities + 0.0679011 * bathroom_luxury – 0.2002360 * privacy

* An increase in the number of persons that the room can accommodate by 1 person will increase the logprice of the room by $0.0827482 when all other variables are held constant
* An increase in number of bathrooms in the room by 1 bathroom will increase the logprice of the room by $0.1859950 when all other variables are held constant
* An increase in in number of bedrooms in the room by 1 bedroom will increase the logprice of the room by $0.1949640 when all other variables are held constant
* An increase in in number of beds in the room by 1 bed will increase the logprice of the room by $0.0232852 when all other variables are held constant
* An increase in in number of amenities in the room by 1 amenity will increase the logprice of the room by $0.0099534 when all other variables are held constant
* An increase in the bathroom_luxury index by 1 unit will increase the logprice of the room by $0.0679011 when all other variables are held constant
* An increase in the privacy index by 1 unit will decrease the logprice of the room by $0.2002360 when all other variables are held constant

# Cluster 4

![model4_new](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Codes/model4_new.png)

![cluster4_model2](https://github.com/Sonull/Unsurvised-Learning-on-Airbnb-LA-data/blob/master/Visualizations/cluster4_model2.png)

# Conclusion
* Thus, the equation of multiple linear regression model for cluster 4 is:
# LogPrice of the room = 3.885959 + 0.102167 * accommodates + 0.153955 * bedrooms + 0.042667 * beds + 0.013965* num_amenities + 0.037928 * bathroom_luxury – 0.176391 * privacy


* An increase in number of persons that the room can accommodate by 1 person will increase the logprice of the room by $0.102167 when all other variables are held constant
* An increase in in number of bedrooms in the room by 1 bedroom will increase the logprice of the room by $0.153955 when all other variables are held constant
* An increase in in number of beds in the room by 1 bed will increase the logprice of the room by $0.042667 when all other variables are held constant
* An increase in in number of amenities in the room by 1 amenity will increase the logprice of the room by $0.013965 when all other variables are held constant
* An increase in the bathroom_luxury index by 1 unit will increase the logprice of the room by $0.037928 when all other variables are held constant
* An increase in the privacy index by 1 unit will decrease the logprice of the room by $0.176391 when all other variables are held constant






