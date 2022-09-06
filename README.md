# Salary_Analysis



### Overview

---

- The purpose of doing this was to learn abit about scraping data, modeling data, visualizing this data in Power BI.
- Fetched data from different sites of German Salaries based on Profession and the State that they live in.
- Also fetched the data of cities, states and the deviation of salaries based on the states.
- After fetching this data, writing this data into different folders in CSV format.
- After writing this data we do some cleaning, transformations and writing that in a so that it can be consumed.
- Profession, State, State_Deviation, City are the tables and then based on these created a Salary_Fact_Table

### Taking it to the next Step

- Used this model in visualization, mostly the data was denormalized it depends on the user how they want to create this data model, either in 3NF and having Surrogate keys and based on that or have a bit denormalized data if your data is not changing much.
- We could have created an ETL pipeline, if we had changing data, or some api that could have provided us with salary based on different factors e.g. Inflation, cost of living etc. But as the this data does not change much so one time csv files would work in this case.
- We are storing this data in csv we would have more tables for more details and based on that also provide some insigths.
---

### Table of Contents
- [Folder Structure](#folder-structure)
- [Executing the Program](#executing-the-program)
- [Task_1](#task_1)
- [Task_2](#task_2)

---


### Folder Structure
- python_file
  - main.py     -> Python file to generate the JSON data
  - data        -> Inside this folder, more folders for JSON, CSV, parquet data to be stored in. 
- Task_1.ipynb  -> This task reads the JSON data does some transformation and writes data in CSV to another folder
- Task_2.ipynb  -> This task reads the CSV data does some transformation and writes data in Parquet to another folder

---

### Executing the Program
- To scrape the data from websites, run all the files that have scrape in them so that Profession, State, City, State_Salary_Deviation is fetched.
- After we 

---

### Task_1
- We use Spark Streaming to read the data from JSON folder and do some tranformation from nested to flat.
- Analytics
  - Clicks
  - Impressions
- Sales
  - Quantity
  - Total_Price
- Datetime
- Provide a schema and change the datatypes of the columns
- Write that data in CSV to a CSV folder.

---

### Task_2

- We use read the data from CSV folder and do some aggregation based on a window with watermark defined
- Use the ForeachBatch to write the data in an append mode

- Reason to use foreachBatch was that when we define the WaterMark of certain time that has to complete before it can write that to the folder
- Lets say we defined a **Window** of 10 seconds and **Watermark** of 30 seconds. The output for this 10 second window will be displayed after 30 seconds when the watermark has passed. 

---
