# IBM-Data-science-Machine-learning-project
In this capstone project, the primary aim will be to predict whether the SpaceX Falcon 9 first stage will land successfully using several machine learning classification algorithms.
Some of the methodologies that were used are as follows:
- Data collection
- Exploratory data analysis
- Visual analytics
- Predictive analytics
-------------------------------------------------------------------------------------------------------------------------

**Introduction**

In this capstone project, we will predict if the SpaceX Falcon 9 first stage will land successfully using several machine learning algorithms. 
SpaceX advertises Falcon 9 rocket launches on its website with a cost of 62 million dollars; other providers cost upward of 165 million dollars each, much of the savings is because SpaceX can reuse the first stage. 
Therefore if we can determine if the first stage will land, we can determine the cost of a launch. This information can be used if an alternate company wants to bid against SpaceX for a rocket launch. Most unsuccessful landings are planned. Sometimes, SpaceX will perform a controlled landing in the ocean. Here, we try to predict for a given set of features about a Falcon 9 rocket launch which include its payload mass, orbit type, launch site, and so on, will the first stage of the rocket land successfully

-------------------------------------------------------------------------------------------------------------------------

**Methods Used to predict**

1. Data Collection & Processing
  - Data collection, wrangling, and formatting, using: SpaceX API
  - Web scraping
2. Exploratory data analysis (EDA)
  - Pandas and NumPy
  - SQL
3. Data visualization
  - Matplotlib and Seaborn
  - Folium
4. Machine learning prediction
  - Logistic regression
  - Support vector machine (SVM)
  - Decision tree
  - K-nearest neighbors (KNN)

-------------------------------------------------------------------------------------------------------------------------

**1. Data collection & Processing** [click here](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/tree/master/Module_1%20_%20Data%20collection)

- Data collection using SpaceX API 
  Modules used: requests, pandas, numpy, datetime.
  - The API used can be found [here](https://api.spacexdata.com/v4/rockets/)
  - The API provides data about many types of rocket launches done by SpaceX, the data is therefore filtered to include only Falcon 9 launches.
  - The API is accessed using requests.get().
  - The json result is converted to a dataframe using the json_normalize() function from pandas.
  - Every missing value in the data is replaced the mean the column that the missing value belongs to.
  - We end up with 90 rows or instances and 17 columns or features.

- Web scraping 
  Modules used: sys, requests, BeautifulSoup from bs4, re, unicodedata, pandas
  - The data is scraped from [List of Falcon 9 and Falcon Heavy launches](https://en.wikipedia.org/w/index.php?title=List_of_Falcon_9_and_Falcon_Heavy_launches&oldid=1027686922).
  - The website contains only the data about Falcon 9 launches.
  - First, the Falcon9 Launch Wiki page is requested from the url and a BeautifulSoup object is created from response of requests.get().
  - Next, all column/variable names are extracted from the HTML table header by using the find_all() function from BeautifulSoup.
  - We end up with 121 rows or instances and 11 columns or features on the created dataframe.

-------------------------------------------------------------------------------------------------------------------------

**2. Exploratory Data Analysis** [click here](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/tree/master/Module_2%20_%20Exploratory%20Data%20Analysis)

- EDA with python libraries
  Modules used: pandas, numpy. Some key insights are as follows
  - The number of launches on each launch site
  - The number of occurrence of each orbit
  - The number and occurrence of each mission outcome
  
- EDA with SQL
  Framework used: IBM DB2
  Modules used: ibm_db. Some key data processed are as follows
  - The names of the unique launch sites in the space mission
  - The total payload mass carried by boosters launched by NASA (CRS)
  - The average payload mass carried by booster version F9 v1.1
  - The SQL statements or functions used include 
  SELECT, DISTINCT, AS, FROM, WHERE, LIMIT, LIKE, SUM(), AVG(), MIN(), BETWEEN, COUNT(), and YEAR().
  
 - EDA with data visualization
  Modules used: Matplotlib & seaborn
   - The relationship between flight number and launch site
   - The relationship between payload mass and launch site
   - The relationship between success rate and orbit type
   - Some of the plots used are scatterplot(), barplot(), catplot(), and lineplot().
  
-------------------------------------------------------------------------------------------------------------------------

**3. Visual analytics** [click here](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/tree/master/Module_3%20_%20VIsual%20analytics)

- Visualization of data
  Modules used: folium, wget, pandas, math
  - Mark all launch sites on a map
  - Mark the succeeded launches and failed launches for each site on the map
  - Mark the distances between a launch site to its proximities such as the nearest city, railway, or highway
  - These are done using functions from folium such as add_child() and folium plugins which include MarkerCluster, MousePosition, and DivIcon.

-------------------------------------------------------------------------------------------------------------------------

**4. Predictive analytics** [click here](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/tree/master/Module_4%20_%20Predictive%20analytics)

- Prediction using multiple machine learning algorithms
  Modules used: pandas, numpy, matplotlib.pyplot, seaborn, sklearn
  - Standardizing the data using the preprocessing.StandardScaler() function from sklearn
  - Splitting the data into training and test data using the train_test_split function from sklearn.model_selection
  - Creating machine learning models, which include: Logistic Regression, Support Vector Machine, Decision Tree, KNN, Decision Tree
  - Fit the models on the training set
  - Find the best combination of hyperparameters for each model using GridSearchCV
  - Evaluate the models based on their accuracy scores and confusion matrix

-------------------------------------------------------------------------------------------------------------------------
**Conclusion**

Rating the machine learning algorithms used on the dataset we can observe that Decision Trees outperforms  all other by a 5% margin. The accuracy scores obtained are sorted from highest to lowest
  1. Decision tree (GridSearchCV best score: 0.8892857142857142)
  2. K nearest neighbors, KNN (GridSearchCV best score: 0.8482142857142858)
  3. Support vector machine, SVM (GridSearchCV best score: 0.8482142857142856)
  4. Logistic regression (GridSearchCV best score: 0.8464285714285713)
