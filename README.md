# Data Sccientist salary estimator: Project Overview
* Created a [tool](https://github.com/trauerj/DS_Salary_project/blob/main/ds_jobs_project_model_building_v1.ipynb) that estimates data science salaries (MAE ~11K-12K$) to help data scientists to negotiate their salary at an interview.
* Engineered features from job description.
* Optimized Linear, Random Forest and Gradient Boosting Regressor using GridsearchCV to reach the best model.

## Code
* Python 3 (ipykernel)
* Packages: pandas, numpy, sklearn, matplotlib, seaborn, plotly
* Dataset source: https://github.com/PlayingNumbers/ds_salary_proj/blob/master/glassdoor_jobs.csv

## Dataset
Columns of the dataset:
*	Job title
*	Salary Estimate
*	Job Description
*	Rating
*	Company 
*	Location
*	Company Headquarters 
*	Company Size
*	Company Founded Date
*	Type of Ownership 
*	Industry
*	Sector
*	Revenue
*	Competitors 

## [Data cleaning](https://github.com/trauerj/DS_Salary_project/blob/main/ds_jobs_project_data_cleaning_and_feature_engineering.ipynb)
I need to clean up the dataset so it was usable for our models. I made the following changes:
* Removed rows with Nan values
* Converted strings to numerics by removing words or letters
* Extract new columns for most required technical skills (Excel, Python, R, SQL, AWS) from job description
* Made a new column if job is in the same state as the HQ or not
* Made a new column if the salary is hourly or not
* Created a new column if the company has a competitor or not
* Convert hourly salaries to annualy salary
* Created new columns for average salary and avarege company size
* Engeneered features like Seniority, Job description length, Simplified job title

## [Data Analysis](https://github.com/trauerj/DS_Salary_project/blob/main/jobs_analysis_v1.ipynb)
I looked at the distribution of the ratings, average salaries, Description length and year of foundation.

I analized the dependence of salary on company size, the company has a competitors or not, in the same state or not, State, Seniority and Job title.

Finaly I looked for if a job require one or more of the most required techical skills.

## [Model Building](https://github.com/trauerj/DS_Salary_project/blob/main/ds_jobs_project_model_building_v1.ipynb)
First, I transformed the categorical variables to dummy variables.

Second, I looked for the 21 most corralated features and made the models using just these features.

I also split the data into train and test sets with a test size 20% in both scenario.

After that, for comparison I scaled the features and fit the models on the scaled features.

I tried three different models:
* Linear Regression - Baseline for the model
* Random Forest Regressor
* Gradient Boosting Regressor

## Model performance
The Random Forest performed best as on the test as on the validation sets.

I got the following MAE values when the models used every features:

* Linear Regression: MAE = 19252
* Random Forest: MAE = 12006
* Gradient Boosting: MAE = 11466

I got the following MAE values when the models used the 21 most corralated features:

* Linear Regression: MAE = 19644
* Random Forest: MAE = 13636
* Gradient Boosting: MAE = 12289

I got the following MAE values when the models used the scaled features:

* Linear Regression: MAE = 19644
* Random Forest: MAE = 12028
* Gradient Boosting: MAE = 11466
