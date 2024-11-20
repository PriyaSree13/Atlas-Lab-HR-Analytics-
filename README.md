
# Atlas Lab HR Analytics in POWER BI
We use the Kimball model approach to develop a Power BI report on HR analytics using a fictional company dataset, Atlas Labs.



## Project Goals : 

- The primary goal is to monitor the key HR metrics on employees.
- The secondary goal is to understand what factors impact attrition. 


## Atlas Lab Dataset Overview :
The database model follows the snowflake schema, making it more granular for our analysis. Refer the details given below for the metadata.  

![image](https://github.com/user-attachments/assets/8d4a1ce4-aec2-4477-8f00-f8a14054d26e)

#### Employee :

| Parameter               | Type     | Description                                                              |
|-------------------------|----------|--------------------------------------------------------------------------|
| `EmployeeID`           | `string` | Unique identifier for each employee                                      |
| `FirstName`            | `string` | The first name of the employee                                           |
| `LastName`             | `string` | The last name of the employee                                            |
| `Gender`               | `string` | The gender of the employee                                               |
| `Age`                  | `string` | The age of the employee                                                  |
| `BusinessTravel`       | `string` | The frequency of business travel for the employee                        |
| `Department`           | `string` | The department in which the employee works                               |
| `DistanceFromHome`     | `string` | The distance between the employee's home and workplace in kilometers     |
| `State`                | `string` | The state in which the employee resides                                  |
| `Ethnicity`            | `string` | The ethnicity of the employee                                            |
| `MaritalStatus`        | `string` | The marital status of the employee                                       |
| `Salary`               | `string` | The annual salary of the employee                                        |
| `StockOptionLevel`     | `string` | The level of stock options granted to the employee                       |
| `OverTime`             | `string` | Whether the employee works overtime (Yes/No)                            |
| `HireDate`             | `string` | The date the employee was hired                                          |
| `Attrition`            | `string` | Whether the employee has left the company (Yes/No)                      |
| `YearsAtCompany`       | `string` | The number of years the employee has been with the company               |
| `YearsInMostRecentRole`| `string` | The number of years the employee has been in their most recent role      |
| `YearsSinceLastPromotion` | `string` | The number of years since the employee's last promotion                 |
| `YearsWithCurrManager` | `string` | The number of years the employee has worked with their current manager   |



#### EducationLevel :

| Parameter             | Type     | Description                                                              |
|-----------------------|----------|--------------------------------------------------------------------------|
| `EducationLevelID`    | `string` | Unique identifier for the education level                                |
| `EducationLevel`      | `string` | The level of education achieved, ranging from "No Formal Qualifications" to "Doctorate" |


#### RatingLevel :

| Parameter             | Type     | Description                                                              |
|-----------------------|----------|--------------------------------------------------------------------------|
| `RatingID`           | `string` | Unique identifier for the rating level                                   |
| `RatingLevel`        | `string` | The performance rating, ranging from "Unacceptable" to "Above and Beyond" |


#### SatisfiedLevel :

| Parameter             | Type     | Description                                                             |
|-----------------------|----------|-------------------------------------------------------------------------|
| `SatisfactionID`      | `string` | Unique identifier for the satisfaction level                           |
| `SatisfactionLevel`   | `string` | The level of satisfaction, ranging from "Very Dissatisfied" to "Very Satisfied" |

#### PerformanceRating :

| Parameter                          | Type     | Description                                                              |
|------------------------------------|----------|--------------------------------------------------------------------------|
| `PerformanceID`                    | `string` | Unique identifier for each performance review                            |
| `EmployeeID`                       | `string` | Unique identifier for the employee being reviewed                        |
| `ReviewDate`                       | `string` | The date of the performance review                                       |
| `EnvironmentSatisfaction`          | `string` | Rating of the employee's satisfaction with their work environment        |
| `JobSatisfaction`                  | `string` | Rating of the employee's satisfaction with their job                     |
| `RelationshipSatisfaction`         | `string` | Rating of the employee's satisfaction with workplace relationships       |
| `TrainingOpportunitiesWithinYear`  | `integer`| Number of training opportunities available to the employee within the year|
| `TrainingOpportunitiesTaken`       | `integer`| Number of training opportunities the employee has taken                  |
| `WorkLifeBalance`                  | `string` | Rating of the employee's work-life balance                               |
| `SelfRating`                       | `string` | The employee's self-assessment rating                                    |
| `ManagerRating`                    | `string` | The manager's rating of the employee's performance                       |






## Reporting Process :

- Requirements Gathering
- Connecting to Datasets 
- Building Data Models 
- Create DAX Measures


## Reporting Process Overview : 

Creating report to track HR Analytics : 
- End-to-End Development Process:
- Loaded four dimension tables and one fact table into Power BI Desktop
- Created data models to streamline the analysis process
- Modeling steps included:
- Creating a calculated date table
- Connecting all dimension tables to their respective fact or dimension tables to establish logical relationships in the data model
- Performed Exploratory Data Analysis (EDA) and created new measures to calculate the attrition rate at Atlas Labs
- The attrition rate formula:
       Attrition Rate = (Number of Employees Who Left / Total Number of Employees) × 100"

## Pre-Processing and creating the Data Models: 

- Firstly, We load our datasets into Power BI desktop and create relations between them. Decide and classify the existing tables as dimensions and facts. 

- Load the datasets and check for any formatting errors or missing values and if the columns are determined with the right datatype. 

- In this scenario, we only have one facts table which is Performance Rating and the rest are classified as dimensions. 

- Connect different data tables together in the form of snowflake schema using active and inactive relationships to attain the logical flow and connections in the datamodel.

- Based on our requirements, We activate the relations between dimension tables. 

<img width="1354" alt="image" src="https://github.com/user-attachments/assets/fb1f6111-f7c9-446e-9281-bcf6cdfa7bbb">

- DATA MODELS: We create a calculated Date table using the DAX code and connect it to the Employee table. 

<img width="765" alt="image" src="https://github.com/user-attachments/assets/3b714254-92d0-498d-bd3c-71ce6b48402e">



## Exploratory Data Analysis 

- Our main objective is to understand attrition at the company.
- We begin the analysis by examining high-level metrics to understand employee trends related to attrition.
- A new measures folder was created to organize all the measures developed during the reporting process.
- Identified active and inactive employees using Employee[Attrition] and calculated the attrition rate.

<img width="211" alt="image" src="https://github.com/user-attachments/assets/a7fc4987-20ac-4b95-90a8-b4f51661d223">


- Attrition rate based on the previous measures.
  
<img width="209" alt="image" src="https://github.com/user-attachments/assets/805e32fb-b076-496c-85ec-c43075491140">

 
- Identify the hiring trends over time to identify where we can identify the biggest growth in new employees. 
insert the image here with the trends over time

- Analyze, How the employees are working within each department and what is the job role that each department is commonly hiring. 
<img width="931" alt="image" src="https://github.com/user-attachments/assets/5a727695-a372-4cb9-aad0-f05a434eaecc">



## The Role of Demographics and Their Impact on Performance

- Histogram sorts the employees by age. We create the age bins for our histogram using Power Query 

- We modify the histogram, to understand the data distribution across multiple Age bins and Gender

- Filter the visual to understand the status of the employee. (We add a page-level filter)

- Marital Status and Ethnicity: We calculate the average salary of the employees based on their ethnicity

<img width="944" alt="image" src="https://github.com/user-attachments/assets/6ed9489f-f67b-4d8b-9dd7-dbd0b8abcdb6">

- Track individual employee's performances scores based on their yearly performance reviews and individual performance reviews. 

## Insights discovered

Key Insights discovered 

- Total Attrition Rate: 16.1%.  
- The Sales department has the highest attrition rate, as Sales Representatives are more prone to churn with a 39.8% attrition rate.
- Employees who have to travel frequently have the highest attrition rate, 24.9%. 
- Employees with longer tenure are less likely to leave their companies.



