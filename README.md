# Module12_Challenge_nosql

# This repository contains 2 Jupyter Notebook codes. This README provides an overview of the code and its functionalities.


# The 1st code imports data from the "establishments.json" file into the "uk_food" database. The data is stored in the "establishments" collection. 


## Database Setup

I imported data, set up the necessary dependencies in this part, and established a connection to the MongoDB database. Here is the associated code to import data:

mongoimport --type json -d uk_food -c establishments --drop --jsonArray --file establishments.json

### Import Dependencies

I import essential dependencies to work with MongoDB and handle data efficiently. These dependencies include:
- `pymongo`: The MongoDB Python driver for connecting to and interacting with the database.
- `pprint`: A library to pretty print data structures for better readability.

### Create an Instance of MongoClient

I created an instance of the MongoClient to establish a connection to the MongoDB database. The `port` parameter specifies the port on which MongoDB is running.

### Confirm Database and Collections

I confirm the creation of the "uk_food" database and list the available databases and collections. This step is crucial for verifying that the database is correctly set up.

### Review a Document in the "establishments" Collection

I retrieve and print a document from the "establishments" collection to review its structure.

## Updating the Database

In this section, I demonstrated how to update the database by inserting a new restaurant, querying data, and making updates.

### Insert a New Restaurant

the dictionary for new restaurant data was provided and inserted into the "establishments" collection using `insert_one`.

### Query the New Restaurant Data

I define a query to find the newly inserted restaurant in the collection and print its details.

### Finding BusinessTypeID

I query the collection to find the "BusinessTypeID" for "Restaurant/Cafe/Canteen" and return specific fields using projection.('BusinessTypeID': 1, 'BusinessType': 1)

### Update BusinessTypeID

I updated the BusinessTypeID of the new restaurant to the correct value using `update_one.

### Count Documents

I count the number of documents with "LocalAuthorityName" as "Dover" to identify how many records match a specific criterion.

### Delete Documents

I delete all documents where "LocalAuthorityName" is "Dover" using `delete_many`.

### Check Remaining Documents

I verified that other documents remain in the collection using `find_one`.

### Update Data Types

I determined the data types of the "longitude" and "latitude" fields and changed them from string to decimal for better compatibility.

### Set Non-Rating Values to Null

I updated non-rating values to `null` for better data integrity.

### Change Data Type for RatingValue

I changed the " RatingValue " data type from string to integer to ensure consistent data types.

### Check Data Type Changes

I verify that the data type changes have been successfully applied to the coordinates and rating values.


# The 2nd code uses MongoDB to update the "uk_food" database, specifically the "establishments" collection. This README provides an overview of the code and its functionalities.

## Database Setup

In this section, I establish a connection to the MongoDB database by creating an instance of MongoClient. I assign the "uk_food" database to a variable name `db`, review the collections in the database, and assign the "establishments" collection to a variable for further operations.

## Querying the Database

### Query Establishments by Hygiene Score

I query the collection to find establishments with a hygiene score of 20. The result is displayed, and I use `count_documents` to determine the number of matching documents.

### Convert to Pandas DataFrame

The query result is converted into a Pandas DataFrame for data analysis. I display the number of rows in the DataFrame and the first 10 rows.

### Query Establishments by Local Authority and RatingValue

I find establishments contain "London" in the Local Authority with a RatingValue greater than or equal to 4. Like the previous query, I display the results, convert them to a Pandas DataFrame, and display the number of rows and the first 10 rows.

### Geographical Query

I perform a geographical query within 0.01 degree on either side of the latitude and longitude of Penang Flavours coordinate. The query looks for establishments with a RatingValue of 5, and the results are sorted by hygiene score. I print the results and convert them into a Pandas DataFrame, displaying the first 10 rows.

### Aggregation Pipeline

I create an aggregation pipeline to perform a series of operations on the data. The pipeline includes matching establishments with a hygiene score of 0, grouping the matches by Local Authority, and sorting them by count. The results are displayed and converted into a Pandas DataFrame, and the number of rows and the first 10 rows are shown.
