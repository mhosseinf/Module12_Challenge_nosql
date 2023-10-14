# Module12_Challenge_nosql

# Importing Data into the uk_food Database

This repository contains Python code to import data from the "establishments.json" file into the "uk_food" database. The data is stored in the "establishments" collection. This README provides an overview of the code and its functionalities.

## Part 1: Database and Jupyter Notebook Setup

I set up the necessary dependencies in this part and established a connection to the MongoDB database.

### Import Dependencies

I import essential dependencies to work with MongoDB and handle data efficiently. These dependencies include:
- `pymongo`: The MongoDB Python driver for connecting to and interacting with the database.
- `pprint`: A library to pretty print data structures for better readability.

### Import data from JSON file in the Resource folder

mongoimport --type json -d uk_food -c establishments --drop --jsonArray --file establishments.json

### Create an Instance of MongoClient

I created an instance of the MongoClient to establish a connection to the MongoDB database. The `port` parameter specifies the port on which MongoDB is running.

### Confirm Database and Collections

I confirm the creation of the "uk_food" database and list the available databases and collections. This step is crucial for verifying that the database is correctly set up.

### Review a Document in the "establishments" Collection

I retrieve and print a document from the "establishments" collection to review its structure.

## Part 2: Updating the Database

In this section, I demonstrate how to update the database by inserting a new restaurant, querying data, and making updates.

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
