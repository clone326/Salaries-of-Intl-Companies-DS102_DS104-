# Project on salaries of international companies (DS102_DS104)
<h3 align="center">Comparing Salaries of International Companies (Jun 2017 - Aug 2021)</h3>
<a name="readme-top"></a>
<br />
<div align="center">
  <a href="https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-">
    <img src="https://onecms-res.cloudinary.com/image/upload/s--ro8YRjsu--/f_auto%2Cq_auto/c_fill%2Cg_auto%2Ch_622%2Cw_830/v1/tdy-migration/20190516_rl_salary.jpg?itok=eho4Q02h" alt="Salaries" width="200" height="200">
  </a>

<div align="left">
  
  ## Table of Contents
  
1. [About the Project](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#about-the-project)
2. [Libraries used](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#libraries-used)
3. [Data Preprocessing](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#data-preprocessing)
      - [Cleaning Companies](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#cleaning-companies)
      - [Cleaning Location](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#cleaning-location)
      - [Cleaning Currencies](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#cleaning-currencies)
4. [Best Paying Company regardless of job positions](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#best-paying-company-regardless-of-job-positions)
    - [Deeper Dive into Netflix](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#deeper-dive-into-netflix)
5. [Best Paying Job Title regardless of Company](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#best-paying-job-title-regardless-of-company)
    - [Deeper Dive into Software Engineering Manager](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#deeper-dive-into-software-engineering-manager)
6. [Scatterplot and Linear Regression for Base Salary vs Exp years](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#scatterplot-and-linear-regression-for-base-salary-vs-exp-years)
5. [Location and Avg Base Salary over time](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#location-and-avg-base-salary-over-time)
6. [Avg Salaries of companies with HQs in at least 10 countries](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#avg-salaries-of-companies-with-hqs-in-at-least-10-countries)
7. [Conclusion & Caveats](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#conclusion-&-caveats)

## About The Project

<div align="left">
This is a Data visualisation project using seaborn, plotly and matplolib to visualise salary data collected from multiple employees from international companies from Jun 2017 to Aug 2021. Questions that I am interested in answering are:
  
1. Best Paying Company
2. Best Paying Job title
3. How much does each year of industrial experience add to one's base salary
4. Insights between Location and Base salary over time
5. Avg base salary across companies that have HQs in at least 10 countries

Data on these inflation drivers was downloaded from <a href="https://www.kaggle.com/datasets/jackogozaly/data-science-and-stem-salaries" alt="Kaggle" width="80" height="80">

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Libraries Used
  ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=plastic&logo=pandas&logoColor=white)\
  ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)\
  ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=plastic&logo=plotly&logoColor=white)\
  ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=plastic&logo=Matplotlib&logoColor=black)\
  ![Custom badge](https://img.shields.io/static/v1?label=seasborn&message=0.12.1&color=informational&style=plastic)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Data Preprocessing
  ### Data Types
  Data columns | dtypes |
  --- | --- 
  timestamp | datetime64[ns] 
  company | object
  level | object
  title | object
  totalyearlycompensation | int64
  location | object
  yearsofexperience | float64
  yearsatcompany | float64
  tag | object
  basesalary | float64

  ### Cleaning Companies
  
  ### Cleaning Location
  
  ### Cleaning Currencies
    
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Best Paying Company regardless of job positions
  
  ### Deeper Dive into Netflix
  
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Best Paying Job Title regardless of Company
  
  ### Deeper Dive into Software Engineering Manager
  
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Scatterplot and Linear Regression for Base Salary vs Exp years
  
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Location and Avg Base Salary over time
    
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Avg Salaries of companies with HQs in at least 10 countries
  
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
  
  ## Conclusion & Caveats
  
  <p align="right">(<a href="#readme-top">back to top</a>)</p>
