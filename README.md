# Salary Analysis



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
- [Program Flow](#program-flow)
- [Folder Structure](#folder-structure)
- [Program Execution](#program-execution)
- [Data Modeling](#data-modeling)
- [Level Up](#level-up)


---

### Program Flow


---


### Folder Structure
- Salary_Analysis
  - Fetch_City_State.ipynb
  - Fetch_Salary_By_Profession.ipynb
  - Fetch_Salary_Deviation_By_State.ipynb
  - Fetch_State.ipynb
  - Spark_City_State.ipynb
  - Spark_Profession.ipynb
  - Spark_State_Deviation.ipynb
  - Spark_Salary_Fact.ipynb
  - Fact (Folder)
  - Profession (Folder)
  - State (Folder)
  - State_Salary_Deviation (Folder)

- The ones starting with **Fetch** will get data from sites and write in a csv file
- The ones with **Spark** will read the csv, tranform the data and write to respective folder.
- The folder will be created after you have executed the Spark code.

---

### Program Execution
- To scrape the data from websites, run all the files that have **Fetch** in them so that Profession, State, City, State_Salary_Deviation is fetched.
```bash
  ipython Fetch_City_State.ipynb
```
```bash
  ipython Fetch_Salary_By_Profession.ipynb
```
```bash
  ipython Fetch_Salary_Deviation_By_State.ipynb
```
```bash
  ipython Fetch_State.ipynb
```
- After we fetched this data and cleaned, tranformed it using Spark we will write this into different folder that will have different CSV files.
```bash
  ipython Spark_City_State.ipynb
```
```bash
  ipython Spark_Profession.ipynb
```
```bash
  ipython Spark_State_Deviation.ipynb
```

- After having these CSV files based on our model we will create Dimensions and Facts and write to another CSV. Spark_Salary_Fact will read all file and write them to Fact Folder.
```bash
  ipython Spark_Salary_Fact.ipynb
```
- Will get this CSV file and start to visualize this data in Power BI.

---


### Data Modeling

<p align="center">
  <img src="Images/Sal_Model.PNG" width="750">
</p>

- The above data model has 3 Dim and 1 Fact and using this Fact we create our visualiztion.
- This data model is not much normalized it depends the use case and what sort of database or warehouse you are using.
- Some warehouses take advantage of joining data, while others are not much performant.

#### Another Model

<p align="center">
  <img src="Images/Another_Sal_Model.JPG" width="750" >
</p>

-  In this model we are using the **Ids** of the Dim tables instead of the names which is a much better practice.
-  If we had more attributes of Dim table we could have moved to a more normalized model but for now denormalized it is.


