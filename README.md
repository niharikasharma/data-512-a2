# data-512-a2
Author - Niharika Sharma

## The goal of the project
The goal of this project is to explore the concept of 'bias' through data on Wikipedia articles following the best practices for open scientific research in designing and implementing a project, and at the same time making the project fully reproducible by others: from data collection to data analysis.

For this project, we are using a dataset of Wikipedia articles with a dataset of country populations. We used a machine learning service called ORES. The ORES API returns the estimated quality of each article.

The analysis we conducted is calculating the proportion (as a percentage) of articles-per-population and high-quality articles for each country. By "high quality" articles we mean either the "FA" (featured article) or "GA" (good article) classes.

The final visualizations and tables are for the following questions that we asked from our final dataset:
1. 10 highest-ranked countries in terms of number of politician articles as a proportion of country population
2. 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population
3. 10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country
4. 10 lowest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country

The following are the steps to do this analysis:
Step 1: Getting the article and population data  
Step 2: Getting article quality predictions   
Step 3: Combining the datasets   
Step 4: Analysis    
Step 5: Tables and Visualization   
Step 6: Documentation    

For running and replicating the final visualization, install all the packages correctly as mentioned in the jupyter notebook and run the Jupyter Notebook. 

## Writeup

From our analysis following are the results that we learned and found:

1. 10 highest-ranked countries in terms of number of politician articles as a proportion of country population

| country | articles   | population  |   percentage   | 
| ------- | :-------: | :-------: | :-------:  |
| Nauru | 53       |  10860 | 0.488029   | 
| Tuvalu | 55    |     11800 | 0.466102   | 
| San Marino | 82      |   33000 | 0.248485  |  
| Monaco | 40    |     38088 | 0.105020   | 
| Liechtenstein | 29    |     37570 | 0.077189 |   
| Marshall Islands | 37      |   55000 | 0.067273  |  
| Iceland | 206  | 330828 | 0.062268   | 
| Tonga | 63 |  103300 | 0.060987   | 
| Andorra  | 34 | 78000 | 0.043590   | 
| Federated States of Micronesia | 38 | 103000 | 0.036893   | 

2. 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population¶

| country    | articles | population  | percentage  |
| ------- | :-------: | :-------: | :-------:  |
| India     |    989 | 1314097616 | 0.000075   |
|     China      |   1138 | 1371920000 | 0.000083  | 
|         Indonesia      |    215 |  255741973 | 0.000084 |  
|         Uzbekistan   |        29  |  31290791 | 0.000093  | 
|         Ethiopia    |      105  |  98148000 | 0.000107   |
|    Korea, North     |      39  |  24983000 | 0.000156   |
|     Zambia     |      26  |  15473900 | 0.000168   |
|       Thailand     |     112  |  65121250 | 0.000172 |  
|  Congo, Dem. Rep. of     |     142  |  73340200 | 0.000194 |  
|   Bangladesh     |     324  | 160411000 | 0.000202   |

#### Countries like Nauru etc don't have a lot of politicians articles being pulished, Nauru has only 53 politician articles, but because their population of 10860 people is extremely low hence the number of articles on politician as a proportion of country population is significantly high for them compared to conutries like China with article count = 1138 and population = 1371920000. 

3. 10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country 

| country  |  percentage |
| -------- | :------: |
| Korea, North | 23.076923 | 
| Saudi Arabia |  11.764706 | 
| Uzbekistan   | 10.344828 | 
| Central African Republic |  10.294118 | 
| Romania  |  9.770115 | 
| Guinea-Bissau |  9.523810 | 
| Bhutan   |  9.090909 | 
| Vietnam  |  8.376963 | 
| Dominica     |  8.333333 | 
| Mauritania   |  7.692308 |  

4. 10 lowest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country

|   country |   percentage |
| ------- | :-------: |
| Tanzania  | 0.245098 |
| Czech Republic |  0.393701 |
|   Morocco |  0.480769 |
|      Fiji  | 0.502513 |
|      Uganda |  0.531915 |
|     Bolivia  | 0.534759 |
|  Luxembourg |  0.555556 |
|      Peru |  0.564972 |
|  Sierra Leone |  0.602410 |

#### It was a big contrast to see a country like North Korea being the highest ranked country in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country. This could be a potential research topic for wikipedia's research and development group, to understand the human diversity and mentoring. 


## License of the source data
[License: MIT](https://opensource.org/licenses/MIT)

## [Figshare Terms and Conditions](https://figshare.com/terms)

## [The Wikimedia Foundation terms of use (LINK)](https://wikimediafoundation.org/wiki/Terms_of_Use/en)


## Link to all relevant API documentation and datasets
The dataset can be found on
1. [Figshare](https://figshare.com/articles/Untitled_Item/5513449)
2. The population data is on the [Population Research Bureau website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)
3. Wikimedia API endpoint for a machine learning system called (ORES)[https://www.mediawiki.org/wiki/ORES]

## Final data file

In the data directory we have three csv.

1. Population Mid-2015.csv - Source ([Population Research Bureau website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)) 
2. page_data.csv - Source ([Figshare](https://figshare.com/articles/Untitled_Item/5513449))
3. final-data.csv	- The final csv created using the ipynb for further analysis. 

We consolidated the data into a single CSV file named final_data.csv in data directory and the description of the values of all fields in the final data file is as follows:  


| Column         | description |  
| -------------- | :---------: |  
|country         | name of the country on which the article is published |
|article_name    | name of the article written on an politician |
|revision_id     | The revision ID to score |
|article_quality | quality of articles about politician (see below to under the categories of the article quality) |
|population      | population per country |


There are 6 quality categories. The options are, from best to worst:
FA - Featured article  
GA - Good article  
B - B-class article  
C - C-class article  
Start - Start-class article  
Stub - Stub-class article

## Known issues or special considerations with the data 
Getting data from the ORES API is a slow process. To reduce the time, we must sent the revision_ids in batch of 50 to 100. Also, if you are parallelizing the process then it is acceptable to use up to four parallel requests.

## Final Visualizations 
1. 10 highest-ranked countries in terms of number of politician articles as a proportion of country population
![alt text](https://github.com/niharikasharma/data-512-a2/blob/master/highest_ranked_countries_number_of_politians_per_article.png)

2. 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population
![alt text](https://github.com/niharikasharma/data-512-a2/blob/master/lowest_ranked_countries_number_of_politians_per_article.png)

3. 10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country
![alt text](https://github.com/niharikasharma/data-512-a2/blob/master/highest_ranked_countries_aritcle_qualitywise.png)

4. 10 lowest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country
![alt text](https://github.com/niharikasharma/data-512-a2/blob/master/lowestest_ranked_countries_aritcle_qualitywise.png)

