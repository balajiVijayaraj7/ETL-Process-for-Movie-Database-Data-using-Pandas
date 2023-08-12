# ETL Process for Movie Database Data using Pandas

## Introduction
Welcome to the ETL (Extract, Transform, Load) process for movie data using Python and the Pandas library. This project demonstrates how to extract movie data from "The Movie Database" using its API, perform data transformations, and load the processed data into a CSV file and a SQLite relational database.

## Extract
In the extraction phase, data was sourced from "The Movie Database" API using an API key. We utilized the API's GET method to request data for 6 movies within a specified range. The data was retrieved in JSON format and converted into a Pandas DataFrame for further processing. The extracted dataset consists of 6 rows and 25 columns.

## Transform
In the transformation phase, several operations were performed:

1. **Column Selection:** A list of columns was created from the main DataFrame and stored in a new DataFrame called `df_bck`.

2. **Genre Transformation:** A new column `genre_name` was added by combining values from the `genre` column (originally in a 'list of dictionaries' format) using a custom function. Each row's genre values were compared with a predefined set of genres to create the `genre_freq` column indicating whether a genre was present or not.

3. **Genre Separation:** The `genre_freq` column was split into separate columns for each categorical value, resulting in a separate DataFrame for genres with a column of lists that were exploded using the `explode().to_list()` method.

4. **Date Transformation:** A new DataFrame was created using the `release_date` column and converted into datetime format.

5. **Runtime Transformation:** The runtime was transformed into hours and minutes format.

## Load
In the loading phase:

1. Three tables, namely 'movies', 'genres', and 'datetimes', were exported to a CSV file.

2. A connection to a SQLite relational database was established. Data frames were loaded into the database, and data was retrieved back from the database for verification.

## Visualization and Verification
The transformed data can be visualized through the generated CSV files and the loaded SQLite database tables. The data is now structured and can be easily queried for analysis or reporting purposes.

## Usage

1. Clone the repository to your local environment.
2. Access the provided Python script that demonstrates the ETL process.
3. Run the script to perform the ETL operations on the movie data.
4. Explore the generated CSV files and the SQLite database to view the transformed data.

## Conclusion

The ETL Process for Movie Database Data using Pandas repository offers a practical example of how to extract, transform, and load data from "The Movie Database" API. By following the outlined steps, you can efficiently process raw data, perform necessary transformations, and store the structured data for further analysis and insights.

Feel free to utilize this repository for learning, adapting, and conducting similar ETL projects using Python and Pandas!

*Note: This repository is intended for educational and practical purposes, showcasing the complete ETL process using Pandas for movie database data.*
