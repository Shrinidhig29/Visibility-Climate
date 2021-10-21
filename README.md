
# Visibility Climate



## 🚀 About Me



I'm a energitic and passionate coder

  
# Hi, I'm SHRINIDHI G! 👋

  
## Demo

Still working on this

  
## Roadmap

**The Problem Statement**

To build a regression model to predict the visibility
distance based on the given different climatic 
indicators in the training data. 

**Data Description**

Data Description: This dataset predicts the visibility distance based on the different indicators as below:

1.	VISIBILITY - Distance from which an object can be seen.
2.	DRYBULBTEMPF-Dry bulb temperature (degrees Fahrenheit). Most commonly reported standard temperature.
3.	WETBULBTEMPF-Wet bulb temperature (degrees Fahrenheit).
4.	DewPointTempF-Dew point temperature (degrees Fahrenheit).
5.	RelativeHumidity-Relative humidity (percent).
6.	WindSpeed-Wind speed (miles per hour).
7.	WindDirection-Wind direction from true north using compass directions.
8.	StationPressure-Atmospheric pressure (inches of Mercury; or ‘in Hg’).
9.	SeaLevelPressure- Sea level pressure (in Hg).
10.	Precip	Total-precipitation in the past hour (in inches).
Apart from training files, we also require a "schema" file from the client, which contains all the relevant information about the training files such as:
Name of the files, Length of Date value in FileName, Length of Time value in FileName, Number of Columns, Name of the Columns, and their datatype.

**Application Architecture and Module vision**

**Code Explaination**
     
- **Data Ingestion**
- **Data Preprocessing and cleaning**
     
    Data Validation 
    In this step, we perform different sets of validation on the given set of training files.  
    - **Name Validation**- We validate the name of the files based on the given name in the schema file. We have created a regex pattern as per the name given in the schema file to use for validation. After validating the pattern in the name, we check for the length of date in the file name as well as the length of time in the file name. If all the values are as per requirement, we move such files to "Good_Data_Folder" else we move such files to "Bad_Data_Folder."

    - **Number of Columns** - We validate the number of columns present in the files, and if it doesn't match with the value given in the schema file, then the file is moved to "Bad_Data_Folder."


    - **Name of Columns** - The name of the columns is validated and should be the same as given in the schema file. If not, then the file is moved to "Bad_Data_Folder".

    - **The datatype of columns** - The datatype of columns is given in the schema file. This is validated when we insert the files into Database. If the datatype is wrong, then the file is moved to "Bad_Data_Folder".


    * **Null values in columns** - If any of the columns in a file have all the values as NULL or missing, we discard such a file and move it to "Bad_Data_Folder".



- **Model Selection**

    Model Training 
    - **Data Export from Db** - The data in a stored database is exported as a CSV file to be used for model training.
    - **Data Preprocessing**   
        - a) Drop columns not useful for training the model. Such columns were selected while doing the EDA.
        - b) Replace the invalid values with numpy “nan” so we can use imputer on such values.
        - d) Check for null values in the columns. If present, impute the null values using the KNN imputer
        - e) Scale the training and test data separately 
    - **Clustering** - KMeans algorithm is used to create clusters in the preprocessed data. The optimum number of clusters is selected by plotting the elbow plot, and for the dynamic selection of the number of clusters, we are using "KneeLocator" function. The idea behind clustering is to implement different algorithms
    To train data in different clusters. The Kmeans model is trained over preprocessed data and the model is saved for further use in prediction.
    - **Model Selection** - After clusters are created, we find the best model for each cluster. We are using two algorithms, "Decision Tree Regressor" and "XGBoost regressor". For each cluster, both the algorithms are passed with the best parameters derived from GridSearch. We calculate the Rsquared scores for both models and select the model with the best score. Similarly, the model is selected for each cluster. All the models for every cluster are saved for use in prediction. 

- **Model Tunning**
- **Prediction**
    - Based on the cluster number, the respective model is loaded and is used to predict the data for that cluster.
- **Logging Framework**
- **Deployment**

**requirements.txt** file consists of all the packages that you need to deploy the app in the cloud.



## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://welcometocodelife.blogspot.com/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shrinidhi-g-ba60b1192/)

  

## Authors

- [@shrinidhig](https://github.com/Shrinidhig29)

  
## Deployment

To deploy this project run

Working on this

  
## Feedback

If you have any feedback, please reach out to us at shrinidhig29@gmail.com

  
