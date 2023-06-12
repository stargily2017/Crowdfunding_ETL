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
1. dict_values = [] initializes an empty list called dict_values used to store the values from each row as dictionaries.
2. for i, row in contact_info_df.iterrows(): starts a loop that iterates through each row in the contact_info_df DataFrame. The loop assigns the index i and the row data row to the variables.
3. data = row['contact_info'] retrieves the value from the 'contact_info' column of the current row and assigns it to the variable data. This value is a string representing a JSON object.
4. converted_data = json.loads(data) uses the json.loads() method to parse the string data into a Python dictionary. The resulting dictionary is assigned to the variable converted_data.
5. row_values = [v for k, v in converted_data.items()] uses a list comprehension to iterate over each key-value pair in the converted_data dictionary. It retrieves only the values (v) from each pair and creates a new list called row_values.
6. dict_values.append(row_values) adds the row_values list, which contains the values from the current row, to the dict_values list. This list will eventually hold all the rows' values as separate lists.
In summary, here we iterate through each row of contact_info_df, where the 'contact_info' column contains JSON strings, convert each JSON string to a dictionary, retrieve the values from each dictionary, and store them as separate lists in the dict_values list. This process essentially converts each row in the DataFrame to a dictionary format and stores the values for further analysis.
