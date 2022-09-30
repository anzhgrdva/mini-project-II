# Miniproject 2

## [Assignment](assignment.md)

## Project/Goals

The main goal of this mini-project is to build a database of restaurants with various names, locations, ratings, addresses, distances, and numbers of reviews using 3 APIs, Pandas, and SQL.

In this project, the starting point is a Waterfront Station in Vancouver, BC and a covered area within a 1km radius.

Using FourSquare, Yelp, and Google APIs' we can compare the quality of the coverage of the area.

## Process

- <ins>Receive API</ins> keys from FourSquare, Yelp, and Google which allow us to set up API clients.
    - for Yelp we are able to find wrapper library, but for Foursquare and Google we use HTTP API directly with requests.
- <ins>Send requests</ins> to each API to collect data in JSON. Create DataFrame from JSON. Check for valid results and filter.
- <ins>Sort DataFrames </ins> with rating and number of reviews columns.
- If not possible to receive all needed data from one API, <ins>make another request</ins> to receive missing information. Merge DataFrames if needed.
- <ins>Create SQLite3 database</ins> on your local machine and store the data we have collected.
- <ins>Save</ins> the schema of the SQLite database we made to a text file.
- <ins>Query</ins> database, compare and present the results.
- <ins>Get</ins> a list of the top 10 restaurants based on their rating.
- <ins>Do</ins> Exploratory Data Analysis on the data we have retrieved.

## Results

Comparing 3 DataFrames that we received, we found that the following restaurants have the highest rating and number of reviews:

    1. Miku
    2. Revolver
    3. Fairmont Pacific Rim

Therefore, you can find 3 tables with top 10 restaurants per each APIs in [this file](/notebooks/EDA.ipynb)

## Challenges

- Data is scattered across multiple endpoints. Getting the exact data that we need for some time could be challenging.
- FourSquare has 10 stars rated system but Yelp and Google – have 5 stars which prevents from making one-to-one comparisons across multiple datasets.
- Google API contains a mix of imperial and metric measurement systems. It took some time to convert miles to meters to equalize all results. That may cost some calculation errors (some of distance results are more than 1 km).
- Some APIs have the type 'restaurant' for not even restaurant places.
- FourSquare API has a limit of 50 results, which could result in missing some of the highest rated places, unfortunately.
- Yelp API doesn't have as much data as we wish.

## Future Goals

- More defensive programming.
- Encapsulate everything in reusable functions.
- More FourSquare API requests.
- Normalize the rating system, so comparative analysis could be done effectively across multiple datasets.
