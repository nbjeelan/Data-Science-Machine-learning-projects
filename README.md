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

1. Data Collection
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

**1. Data collection**

1.1 Data collection using SpaceX API
[Module_1.1_Data_collection_using_api](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/blob/322af1b760e7f25397d93f0de2247e68e28aab6f/Module_1%20_%20Data%20collection/01.%20jupyter-labs-spacex-data-collection-api.ipynb)
  - Libraries or modules used: requests, pandas, numpy, datetime.
  - The API used can be found [here](https://api.spacexdata.com/v4/rockets/)
  - The API provides data about many types of rocket launches done by SpaceX, the data is therefore filtered to include only Falcon 9 launches.
  - The API is accessed using requests.get().
  - The json result is converted to a dataframe using the json_normalize() function from pandas.
  - Every missing value in the data is replaced the mean the column that the missing value belongs to.
  - We end up with 90 rows or instances and 17 columns or features.

1.2 Web scraping
[Module_1.2_Web_scraping](https://github.com/nbjeelan/IBM-Data-science-Machine-learning-project/blob/322af1b760e7f25397d93f0de2247e68e28aab6f/Module_1%20_%20Data%20collection/02.%20jupyter-labs-webscraping.ipynb)
  - Libraries or modules used: sys, requests, BeautifulSoup from bs4, re, unicodedata, pandas
  - The data is scraped from [List of Falcon 9 and Falcon Heavy launches](https://en.wikipedia.org/w/index.php?title=List_of_Falcon_9_and_Falcon_Heavy_launches&oldid=1027686922).
  - The website contains only the data about Falcon 9 launches.
  - First, the Falcon9 Launch Wiki page is requested from the url and a BeautifulSoup object is created from response of requests.get().
  - Next, all column/variable names are extracted from the HTML table header by using the find_all() function from BeautifulSoup.
  - A dataframe is then created with the extracted column names and entries filled with launch records extracted from table rows.
  - We end up with 121 rows or instances and 11 columns or features.
