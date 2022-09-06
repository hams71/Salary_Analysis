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
- [Folder Structure](folder-strucuture)
- [Executing the Program](executing-the-program)
- [Fetching Data]
- [Modeling]
- [Taking It To The Next Step]


---


### Folder Structure

---

### Executing the Program
- To scrape the data from websites, run all the files that have scrape in them so that Profession, State, City, State_Salary_Deviation is fetched.
- After we fetched this data and cleaned, tranformed it we will write this into different folder that will have different CSV files.
- After haviing these CSV files based on our model we will create Dimensions and Facts and write to another CSV.
- Will get this CSV file and start to visualize this data in Power BI.

---
