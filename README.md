
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


## Reporting process

Creating report to track HR Analytics : 
- end-to-end development process
- loaded 4 dimensions and one facts table onto power bi desktop 
- Now we created data models / data modeling to ease the analysis process 
- Modeling : Create a calculated date table ( mention the code used and explain each and every line of the code using chat gpt)
- Connect each and every dimension tables to the respective facts or dimensions table to attain the logical flow and connections in the datamodel. 
- Perform EDA and create new measures to calculate the attrition rate in the Atlas Lab 
- Explain the formula for the Attrition rate ( here and add the card visuals screenshots)
## Pre-Processing and creating the Data Models: 

- Firstly, We load our datasets into Power BI desktop and create relations between them. Decide and classify the existing tables as dimensions and facts. 

- Load the datasets and check for any formatting errors or missing values and if the columns are determined with the right datatype. 

- In this scenario, we only have one facts table which is Performance Rating and the rest are classified as dimensions. 

- Connect different data tables together in the form of snowflake schema using active and inactive relationships to attain the logical flow and connections in the datamodel.

- Based on our requirements, We activate the relations between dimension tables. 

<img width="1354" alt="image" src="https://github.com/user-attachments/assets/fb1f6111-f7c9-446e-9281-bcf6cdfa7bbb">

- DATA MODELS : We create a calculated Date table using DAX code and connect it to the Employee table. 

<img width="765" alt="image" src="https://github.com/user-attachments/assets/3b714254-92d0-498d-bd3c-71ce6b48402e">



## Exploratory Data Analysis 

- Our main objective is to understand attrition at the company.
- We begin the analysis by examining high-level metrics to understand employee trends related to attrition.
-  A new measures folder was created to organize all the measures developed during the reporting process.
- Identified active and inactive employees using Employee[Attrition] and calculated the attrition rate.
insert the DAX formula picture and the card viz ****

- Attrition rate based on the previous measures. 
- Identify the hiring trends overtime to identify where we can identify the biggest growth in new employees. 
insert the image here with the trends over time

- Analyze, How the employees are working within each department and what is the job role that each department is commonly hiring. 

insert the viz****


## The Role of Demographics and Their Impact on Performance

- Histogram sorts the Emoployees by age. We create the age bins for our histgram using Power Query 

Insert the image of bins creation in power query ***
Insert the histogram 

- We modify the histogram, to understnad the data distribution across multiple Age bins and Gender

- Filter the visual to understand the status of the employee. (We add a page level filter)

insert the final filtered image ( ***** ) that explains the data distribution across diff age groups and gender 

- Marital Status and Ethnicity : We calculate the average salary of the employees based on their ethnicity

Insert the image here *****

- Track individual employee's performances scores based on their yearly performance reviews and  individual performance reviews

Insert the performance trackers and the metrics used. 




## Insights discovered and the final coheisve report 

Key Insights discovered 

- % attrition rate : insert image and nuemricals ( for each department and job role)
- % Attrition Rate Date  : attrition rate based on HireDate 
- Conclude the department and the jobn role where immedidate attention is required by the Hr department to improve the process to reduce the customer churn in the respective areas. 
-  Other factors affecting the attrition rate and descrieb their metircs here 
insert the visuals, " attrition by overtime requirement ", " Attrition by Tenure ", 



Insert the final report view*****
