# Final-Project_DATA1202
For this project, I sourced for a relatable dataset on Kaggle. Please see attached the link to the dataset https://www.kaggle.com/datasets/arnavsmayan/netflix-userbase-dataset

The dataset provides a snapshot of a sample Netflix userbase, showcasing various aspects of user subscriptions, revenue, account details, and activity. Each row represents a unique user, identified by their User ID. The dataset includes information such as the user's subscription type (Basic, Standard, or Premium), the monthly revenue generated from their subscription, the date they joined Netflix (Join Date), the date of their last payment (Last Payment Date), and the country in which they are located.

Research Question- Calculate the number of Netflix subscribers within an age group by their countries and generate insights.

Steps for Dimension and Facts table 
•	The sourced dataset for Netflix userbase was the dimension table. 
•	A split of the main table was done with user ID being the unique identifier and common attribute, the table also included the countries, revenue, and age details. 
•	I went ahead to create age groups on the table. 
-	Ages 20-29 (Twenties) 
-	Ages 30-39 (Thirties)
-	Ages 40-49 (Forties) 
-	Ages 49-59 (Fifties)

ETL PROCESS

DATA EXTRACTION 

The first step I carried out was to load mysql and ensure connection was intact. I created a schema called final_project after which I tried to import both the dimension and fact table using the table data import wizard option however I experienced an issue/error while trying to load my table, so I started to troubleshoot and realised it was the format of csv my tables were saved as. I updated the format for both tables to (macintosh csv) and I was able to import both tables successfully. 
•	Screenshot for select statement done for both tables can be found in the snapshot folder in the GitHub repository provided.

DATA TRANSFORMATION

The first step I carried out here was to create a select statement on the dimension table that was initially loaded, I JOINED my two tables on their common column called User ID and did a count with a case syntax to calculate the number of Netflix subscribers within an age group by their countries. I also did a GROUP BY This clause was done to group the results by the specified Country. The overall purpose of this transformation was to answer the research question and derive the number of subscribers within an age group by countries and the following insights were deduced. 

•	The United States and Canada have the highest user counts across all age groups.
•	Spain also has a substantial user count in all age groups, indicating strong Netflix usage.
•	European countries like the United Kingdom, Germany, France, Spain, and Italy exhibit consistent patterns, with larger user counts in the 'Thirties' and 'Fourties' age groups.
•	Focusing on retaining users in their 'Thirties' and 'Fourties' could be important, as these age groups represent significant portions of the user base.
•	The 'Fifties' age group has relatively lower user counts across all countries. This could imply that older users might not be as engaged with the platform compared to younger users.

DATA LOADING 

For the process of data loading, the SQL statement CREATE VIEW new_dataset AS was used to create a new virtual table, referred to as a "view," named "new_dataset." This view is based on the results of the SQL query that joins and aggregates data from the two different tables: "netflix userbase data" and "split table for netflix". By creating this view, I was effectively creating a saved query that presents aggregated and structured data from the original tables so whenever you query the "new_dataset" view, it will execute the underlying query and provide you with the aggregated user counts by age group and country without needing to recreate the query every time. I did not experience any issues while doing this. 

REFLECTIONS 

Learning from the Project:

•	SQL Proficiency: Engaging in this project enhanced my skills in writing SQL queries, especially complex ones involving joins, aggregations, and the creation of views.
•	Data Interpretation: Working with datasets and generating insights helped improve my ability to interpret and draw meaningful conclusions from a random dataset.
•	Data Manipulation: The project reinforced skills in data manipulation, including filtering and grouping.

Challenges:

•	Query Complexity: Working with multiple tables was a little complex and crafting the research question to be answered.
•	Joining Data: I struggled a bit while trying to join my tables, it was a little complex. I was getting multiple outputs at first, so I had to research a lot on how to resolve it online. 

In totality it was a very insightful experience as I was able to put all the SQL learnings from the semester into use and learn from my mistakes.

I have created 2 folders (Code and Snapshot) for the full details of the work done in this project.
