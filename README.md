# Assignment-3-Data-Transformation-and-Data-Modeling
Assignment 3: Data Transformation and Data Modeling
Data Transformation:
● Restrict the "List of Orders" table to only the first 500 rows.

Sol: Home --> Keep Rows--> Keep top rows --> Specify 500--> ok

● Ensure the “Order Date” column in the “List of Orders” table is set to data type 'Date'.

Sol: Select the column --> Right click ---> change type 

● Change the data type of “Amount” and “Target” columns to ‘Fixed Decimal Number’.

Sol: Select the column --> Right click ---> change type

● Format the "CustomerName" column into proper case, ensuring consistent
capitalization for each word.

Sol: select column --> Transform tab --> Format --> capitalize each word

● Merge the "State" and "City" columns to create a new column named "Location" in
the format ‘City, State’.

Sol : Select both column in the specified order --> transform --> Merge columns --> Specify separator and name --> ok

● Create a new custom column named "Profit Margin" as the percentage of "Profit"
divided by "Amount".

Sol: select the column ---> Add column tab --> Custom column --> Specify the name and formula ---> ok
	Right click on the new column created --> change type --> percentage

NOTE: Columns used in the formula should have the datatype compatible or almost same

● Add a new conditional column named "Profit Status" based on the values in the
"Profit" column. The conditions are as follows: if the profit is less than 0, the label
should be "Loss"; if the profit equals 0, the label should be "Break-Even"; and if the
profit is greater than 0, the label should be "Profit".

Sol: Select the column --> Add column --> Conditional column --> Specify the columnname and conditions --> ok

Merging Data (Joins):
● Merge the "List of Orders" and "Order Details" tables into a new single table named
"Orders Data" based on the "Order ID" relationship.

Sol : In the Queries pane , select listoforders table --> Home --> Merge Queries --> MergeQueries as new --> Will show ListOfOrders --> 	Select OrderDetails --> Click on OrderId column in both tables shown --> Select the join Kind --> Ok

	In the Queries pane, name the table as OrdersData  ---> Table Data shown click on OrdersDetails column appeared --> click on expand icon --> Uncheck Select all columns and check only specific details that we require --> Uncheck "Use original columnname as prefix" --> ok

Handling Missing Data & Duplicate Data:
● Identify missing values in the data and determine a strategy to address them.

NOTE: There is no missing values or blank values in any columns as I used "Inner Join" as the join kind to create Orders Data table
	View tab --> check the boxes for column quality, column profile and column distribution as needed

Sol : To replace ---> Right click on the column --> Replace values --> Specify value to find and replace value with --> ok
OR	Add column ---> conditional column

● Check for duplicate rows and define a strategy to handle duplicates.

Sol: View tab --> Column profile (Gives us duplicates in each column)
	Select all columns or entire data with headers --> Home --> Remove rows --> Remove duplicate rows (Removes duplicates based on a row)

Sorting and Filtering Data:
● In the ‘Orders Data’ table, utilize sorting and filtering techniques on columns like
Order Date, State or Category to analyze data based on specific criteria:
◆ Sort the orders by Order Date in descending order to analyze recent trends.

Sol: Click the drop down in the order date --> Sort descending

◆ Filter the orders to focus only on a specific state (e.g., Tamil Nadu) for
regional analysis.

Sol: Click the drop down in the State --> Uncheck select all and check which state you need

Grouping and Aggregating Data:
● Duplicate the “Order Details” table and calculate the count of each Order ID, average
profit by Category or total amount by Sub-Category.

Sol: On the Queries pane --> Right click on Order Details --> Duplicate ---> Rename to Order_Details_Summary
	
Tranform tab --> Group By --> Advanced --> Select Order ID (and add Category using the Add grouping button)
New column name: Total Orders Count | Operation: Count Rows --> Click Add aggregation:

New column name: Average Profit | Operation: Average | Column: Profit --> Ok


● Duplicate the “Sales Target” table and aggregate the total target amount by Month of
Order Date.

Sol: On the Queries pane --> Right click on Sales Target --> Duplicate ---> Rename to Sales_Target_By_Month
	
Tranform tab --> Group By --> Basic --> Select Month of Order Date
New column name: Total Target Amount | Operation: Sum | Column: Target --> Ok


Data Modeling:
● Establish a relationship between the “List of Orders” and “Order Details” tables using
the ‘Order ID’ column.

Sol : Modelling --> manage Relationships --> Delete existing relationships

Modelling --> Manage Relationships --> New relationship ---> Select From table then To Table --> Click on the key column "Order ID" --> Provide Cardinality --> Specify Cross filter Direction -->Check Make this relationship active --> ok

● Build a relationship between the “Order Details” and “Sales Target” tables based on
the ‘Category’ column. Click "Manage relationships" and ensure this relationship is
active

Sol : Modelling --> manage Relationships --> Delete existing relationships

Modelling --> Manage Relationships --> New relationship ---> Select From table then To Table --> Click on the key column "Category" --> Provide Cardinality --> Specify Cross filter Direction --> Check Make this relationship active --> ok
