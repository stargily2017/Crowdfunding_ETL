# Crowdfunding_ETL
A Category DataFrame is Created (15 points)
The DataFrame contains a "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories (5 points)
The DataFrame has a "category" column that contains only the category titles (5 points)
The category DataFrame is exported as category.csv (5 points)
A Subcategory DataFrame is Created (15 points)
The DataFrame contains a "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories (5 points)
The DataFrame contains a "subcategory" column that contains only the subcategory titles (5 points)
The subcategory DataFrame is exported as category.csv (5 points)
A Campaign DataFrame is Created (30 points)
The DataFrame has the following columns: (25 points)
A "cf_id" column
A "contact_id" column
A "company_name" column
A "description" column
A "goal" column that is a float data type
A "pledged" column that is a float data type
An "outcome" column
A "backers_count" column
A "country" column
A "currency" column
A "launch_date" with the time formatted as "YYYY-MM-DD"
An "end_date" with the time formatted as "YYYY-MM-DD"
A "category_id" column that contains the unique identification numbers matching those in the "category_id" column of the category DataFrame
A "subcategory_id" column that contains the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame
The campaign DataFrame is exported as campaign.csv (5 points)
A Contacts DataFrame is Created (15 points)
The DataFrame has the following columns: (10 points)
A "contact_id" column
A "first_name" column
A "last_name" column
An "email" column
The contacts DataFrame is exported as contacts.csv (5 points)
A Crowdfunding Database is Created (25 points)
A database schema labeled, crowdfunding_db_schema.sql is created (5 points)
A crowdfunding_db is created using the crowdfunding_db_schema.sql file (5 points)
The database has the appropriate primary and foreign keys and relationships (5 points)
Each CSV file is imported into the appropriate table without errors (5 points)
The data from each table is displayed using a SELECT * statement (5 points)
This project will be evaluated against the requirements and assigned a grade according to the following table:

# Iterate through the contact_info_df and convert each row to a dictionary.
import json
dict_values = []
for i, row in contact_info_df.iterrows():
    data = row['contact_info']
    converted_data = json.loads(data)
    # Iterate through each dictionary (row) and get the values for each row using list comprehension.
    row_values = [i for j, i in converted_data.items()]
    # Append the list of values for each row to a list. 
    dict_values.append(row_values)
print(dict_values)
