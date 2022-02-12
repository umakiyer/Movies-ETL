# Movies-ETL 
Created a movie database from multiple data sources.
Extracted the data from multiple data sources. Transformed multiple data using RegEX( dropping/merging the columns) & created DataFrame. Converted the DataFrame to create the movie database. Loaded the movie database to pgAdmin. Wrote SQL query to verify the movie database.

## ETL function to read the data:    

* Created function to read the Wikipedia , kaggle data, rating data. 

Raw Wikipedia data :

![image](IMAGES/del1_wiki.PNG)

Raw Kaggle data :

![image](IMAGES/del1_kaggle.PNG)

Raw Ratings data :

![image](IMAGES/del1_ratings.PNG)

## ETL for the Wikipedia data :  
* Loaded & converted the json file to DataFrame.
* By calling the clean_movie function, merged columns with of different languages to alternate title. Renamed the columns to appropiate headings.
* Removed the TV shows from the data.
* Created imbd_id & dropped the duplicate rows.
* Parsed the box-office, budget, running time & release date column using regex.
* After the ETL, the number of columns decreased to 23 from 193!

Cleaned Wikipedia Data :

![image](IMAGES/wiki_movies_df.PNG)

Wikipedia Columns List:

![image](IMAGES/wiki_movies_columns.PNG)

## ETL for the Kaggle metadata data : 
* Loaded the data into the DataFrame.
* Parsed the data on adult,video,budget,id,popularity & release date columns.
* Merged the clean wWkipedia data & Kaggle data. 
* Filled the missing Kaggle data from the Wikipedia data & named the new DataFrame as 'movie'.
* Renamed the columns in the merged data.
* Merged the rating data into the merged movie data.

Movie DataFrame :
![images](IMAGES/del2_kaggle2.PNG)

Movie data with Rating data merged

![images](IMAGES/del2_kaggle1.PNG)

## Create Movie Database : 
* Created the movie database in pgAdmin4.
* Imported the dependency SQLACHEMY & psycopg2.
* Created the movie table in pgAdmin.

The movie  tables & the number of rows in the table:

![image](IMAGES/del4_table.PNG)

![image](IMAGES/movies_table.PNG)

* Created the rating tables in chunks of 100,000 as there were 260K rows.

![image](IMAGES/creating_ratings_table.PNG)

* Top 10 rows of the rating table & number of rows:

![image](IMAGES/del4_ratings.PNG)

![image](IMAGES/ratings_table.PNG)



