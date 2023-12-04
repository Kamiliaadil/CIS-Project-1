# CIS-Project-1

Predict the Risk of 10-Year Heart Disease CHD

   1.	Problem statement:
   
This project aims to predict the 10-year risk of heart disease using health information from 4,238 individuals. The dataset includes factors like gender, age, smoking habits, medications, diabetes, BMI, heart rate, glucose levels, education level, hypertension, stroke history, cholesterol levels, and systolic and diastolic blood pressure.
The goal is to classify individuals into two categories: having heart disease or not having heart disease. The primary motivation is to enhance risk prediction strategies for early identification of at-risk individuals and effective heart disease prevention.
While the project demonstrates significant potential, there are certain limitations to address. The dataset size may impact the complexity and reliability of the machine-learning models. Additionally, accurately predicting heart diseases can be challenging due to uncertainties, such as unaccounted lifestyle choices and other influencing factors.

   2. Literature review:
    
In recent years, heart disease prediction has garnered substantial attention due to its potential in early risk identification and prevention strategies. Researchers have explored various approaches to predict heart disease, ranging from traditional risk factors such as age, gender, and cholesterol levels to more advanced techniques involving machine learning and data mining. Prior studies have emphasized the significance of accurate risk assessment, aiming to mitigate the global burden of heart disease. While some research has focused on individual risk factors, others have leveraged comprehensive datasets to develop predictive models capable of identifying individuals at high risk. These endeavors reflect the growing importance of employing data-driven methodologies to enhance heart disease prediction, ultimately contributing to improved patient care and health outcomes.

   3.	Data description:
   
The data I'm working with comes from the Framingham Heart Study, a project that tracks lots of people to learn about heart disease. I'm using a specific part of this data that focuses on predicting heart disease risk over 10 years.
This data comes from around 4,238 individuals and is part of an ongoing research effort in Framingham, Massachusetts. It's stored in a CSV file and has 16 columns with 15 different things we're interested in. These things include stuff like age, whether people smoke or take medications, and whether they have diabetes or high glucose levels. We're particularly looking at whether someone might get heart disease in the next 10 years.
These attributes collectively offer a comprehensive insight into various facets influencing heart health. The dataset features a mix of categorical and numerical variables, representing demographic, behavioral, and medical risk factors. People willingly shared their health information to contribute to this dataset, making it more real and useful for figuring out predictions about heart disease.

   4.	Methodology:
      
To ensure the integrity of my data, I began by conducting exploratory data analysis and employing data visualization techniques. Initially, I checked for missing values in the dataset and filled them using the mean value. This decision was made to retain important variables without losing valuable data. I also decided to exclude the education column from the analysis, as I believe that the level of education is not a substantial factor in predicting heart disease.
Next, I examined the dataset for any anomalies through descriptive statistics. The analysis revealed the need for data scaling due to varying ranges of data points across features. To gain insights into variable correlations and their impact on the target variable, I performed a correlation analysis. This helped identify significant relationships among different variables.
Utilizing data visualization, I employed the Seaborn library to create box plots for categorical variables and cat plots to visualize numerical variables. This step assisted in spotting outliers, assessing target variable imbalance, and understanding how different features relate to the risk of heart disease. With preprocessing complete, I moved on to preparing the dataset for machine learning.
My initial step involved splitting the data into two parts: X, which contains features, and Y, representing the Ten-Year CHD. To establish a 70-30 ratio between training and testing data, I employed Scikit Learn's train_test_split function. For consistency, I then scaled the data using the Standard Scaler from Scikit Learn. Given the imbalanced target variable, I used the SMOTE oversampling technique to address this. I also used cross-validation for all models. This technique helps assess how well the models generalize to new data and detect overfitting or underfitting problems.
With the dataset prepped, I embarked on training our models. Given the binary nature of the problem, I sought to let the models learn from 70% of our dataset. To achieve this, I considered an array of supervised machine learning algorithms designed for classification tasks, such as Decision Trees, KNN, Gaussian Naive Bayes, Random Forest, Logistic Regression, Linear SVM, RBF SVM, Poly SVM, and Sigmoid SVM. Additionally, I explored unsupervised machine learning via K-means clustering.
In evaluating the models, my focus was on determining the most suitable one for predicting the 10-year heart disease risk. I achieved this by comparing the classification reports for each model, assessing factors like accuracy, precision, recall, and f1-score.
After identifying the best-performing model, I will proceed to deploy it within a Python environment, leveraging Flask. This will enable non-technical users to access and utilize the model without any complexities. My ultimate aim is to make a positive impact by facilitating the early detection of heart disease risk for a wider audience.

   5.	Results:
      
The analysis of the dataset and subsequent machine learning model evaluation revealed significant insights into predicting the 10-year risk of heart disease. During the exploratory data analysis, a correlation matrix highlighted strong correlations between certain variables, such as "prevalentHy" with "psysBP" (0.7) and with "diabBP" (0.6). However, the correlation analysis with the target variable "TenYearCHD" demonstrated that no column exhibited a substantial correlation with the dependent variable.
Data visualization further unveiled that the target variable was imbalanced, with approximately 85% of individuals not having heart disease and only 15% having heart disease. To address this, the minority class was oversampled, resulting in a balanced representation. Additionally, the visualization indicated the presence of outliers for variables such as 'glucose', 'BMI', 'heartRate', 'totChol', 'sysBP', and 'diaBP', prompting their removal.
I evaluated the machine learning classifiers and looked at various metrics. I also paid attention to accuracy, precision, recall, and the f1-score to get a complete picture of how well the models performed.

Among the classifiers, the Decision Trees (DT) model showed an accuracy of 78%, with a precision of 0.79, a recall of 0.78, and an f1-score of 0.78. The K-Nearest Neighbors (KNN) model achieved an accuracy of 87%, along with a precision of 0.77, a recall of 0.87, and an f1-score of 0.82. The Gaussian Naive Bayes (GNB) classifier had an accuracy of 82%, with a precision of 0.81, a recall of 0.82, and an f1-score of 0.81. The Random Forest Classifier (RFC) displayed an accuracy of 87%, a precision of 0.82, a recall of 0.87, and an f1-score of 0.82. The Logistic Regression (LR) model had an accuracy was 87%, with a precision of 0.81, a recall of 0.87, and an f1-score of 0.82. The Polynomial SVM scored an accuracy of 87%, a precision of 0.80, a recall of 0.87, and an f1-score of 0.82. Lastly, the Sigmoid SVM model achieved an accuracy of 82%, a precision of 0.80, a recall of 0.82, and an f1-score of 0.81.

When we look at the AUC scores, the Decision Trees (AUC = 0.84) showed moderate ability to distinguish between heart disease and non-heart disease cases. The K-Nearest Neighbors (AUC = 0.87) demonstrated good differentiation between the classes. The Gaussian Naive Bayes (AUC = 0.89) displayed strong capability in identifying heart disease cases. The Random Forest (AUC = 0.92) excelled with an excellent AUC score, showing remarkable ability in classifying heart disease cases. The Logistic Regression (AUC = 0.91) achieved a very good AUC score, effectively distinguishing between the two classes. The Support Vector Machine (AUC = 0.91) presented strong discriminatory ability, indicating proficiency in separating heart disease cases.

The K-Means algorithm. I identified an "elbow" point at K = 3, which suggests that this could be an optimal number of clusters for the dataset. Across various distance metrics like Euclidean, squared Euclidean, Manhattan, Chebyshev, Canberra, and chi-square distances, the purity score consistently stayed high at 86.82%. This consistent score shows that the clusters are relatively pure. However, when I visually inspected the three clusters, I noticed that they were spread vertically and not very well separated. This might mean that the clusters are not distinct, and the centroids are quite far from where the actual data points are gathered. This observation hints that the K-Means algorithm might not be effectively capturing the complex data patterns.

To conclude, I found that the Random Forest classifier displayed the strongest performance across various classification report metrics, including accuracy, precision, recall, and f1-score. Moreover, it boasted the highest AUC score, signifying its exceptional predictive ability. Given these results, I intend to proceed with the deployment of the Random Forest classifier within a Python environment to further explore its practical utility
 

















 

 


 


 

