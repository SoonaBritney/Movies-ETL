# Movies-ETL

1. Overview

Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs your help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

2. Solution:
1) Deliverable 1 (Extraction): Write an ETL Function to Read Three Data Files
https://github.com/SoonaBritney/Movies-ETL/blob/main/ETL_function_test.ipynb
We read 3 files below, created the lists and then converted as the panda dataframes.  
    - movies_metadata.csv  ==> kaggle_file ==> Kaggle_metadata (dataframe) 
    - ratings.csv ==> ratings_file ==> Ratins (dataframe) 
    - wikipedia-movies.json ==> wiki_file ==> wiki_movies_df (dataframe) 

2) Deliverable 2 (Data Cleansing): Extract and Transform the Wikipedia Data
https://github.com/SoonaBritney/Movies-ETL/blob/main/FTL_clean_wiki_movies.ipynb
Using the above dataframe, we will do the data cleansing.
    - try-catch: block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs. 
    - The extraction and transformation of the Wikipedia data in the ETL function does the following:
    - A list comprehension is used to keep columns with non-null values. 
    - The non-null box office data is converted to string values using the lambda and join functions. 
    - A regular expression is used to match the six elements of "form_one" of the box office data. 
    - A regular expression is used to match the three elements of "form_two" of the box office data. 
    - The following columns are cleaned in the Wikipedia DataFrame: 
        - The box office column: to display well formatted decimal number  
        - The budget column:to display well formatted decimal number 
        - The release date column:to display well formatted daytime
        - The running time column:to display well formatted in minutes 

After cleansing, the cleaned Wikipedia data is converted to a Movies_df Pandas DataFrame, and the DataFrame is displayed in the deliverable 2. 
 
3) Deliverable 3: Extract and Transform the Kaggle data
https://github.com/SoonaBritney/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb
    We cleaned 2 data frames (wiki_movies_df, and Kaggle_metadata), and merged into the movies_df dataframe.
    We will iterate to find out the columns to keep, and fill the missing data in Kaggle, rearrange the columns, and renames them. An, we will transform and merge with ratings. 


4) Deliverable 4: Create the Movie Database
https://github.com/SoonaBritney/Movies-ETL/blob/main/ETL_create_database.ipynb
 Once all is done, we will create sql script to convert to sql database tables (movies, ratings)

All the screenshots are here:
https://github.com/SoonaBritney/Movies-ETL/tree/main/resources

I did not include the csv files in the GitHub to avoid large file errors.  