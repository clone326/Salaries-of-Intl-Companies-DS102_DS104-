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
      - [Cleaning Countries](https://github.com/clone326/Salaries-of-Intl-Companies-DS102_DS104-/edit/main/README.md#cleaning-countries)
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
  
  Issue: Many inconsistencies for data input on company names
  
  Amazon example:
  
  Listing out Amazon Company name variations
  ```sh
  sort_amazon_1 = df_data_science_salaries['company'].str.contains('A', na = False)
  sort_amazon_2 = df_data_science_salaries['company'].str.contains('a', na = False)
  sort_amazon_3 = df_data_science_salaries['company'].str.contains('M', na = False)
  sort_amazon_4 = df_data_science_salaries['company'].str.contains('m', na = False)
  sort_amazon_5 = df_data_science_salaries['company'].str.contains('Z', na = False)
  sort_amazon_6 = df_data_science_salaries['company'].str.contains('z', na = False)
  sort_amazon_7 = df_data_science_salaries['company'].str.contains('N', na = False)
  sort_amazon_8 = df_data_science_salaries['company'].str.contains('n', na = False)

  df_data_science_salaries[(sort_amazon_1 | sort_amazon_2) & (sort_amazon_3 | sort_amazon_4) & (sort_amazon_5 | sort_amazon_6) & (sort_amazon_7 | sort_amazon_8)].company.unique()
  ```
  Output Amazon example:
  
  ![image](https://user-images.githubusercontent.com/113367891/213163335-6aff8722-fc8b-43cb-bd97-9370db5a47b5.png)

  Solution: Replacing values and Double checking
  ```sh
  
  df_data_science_salaries['company'].replace(to_replace=['amazon','Amazon web services','amzon','Amzon','AMAZON','Amazon Web Services','Amazon.com','AMazon'], value = 'Amazon', inplace= True)

  df_data_science_salaries[(sort_amazon_1 | sort_amazon_2) & (sort_amazon_3 | sort_amazon_4) & (sort_amazon_5 | sort_amazon_6) & (sort_amazon_7 | sort_amazon_8)].company.unique()
  ```
  Output after cleaning:
  
  ![image](https://user-images.githubusercontent.com/113367891/213163573-6a47f14a-eb70-4a28-b3f1-c35c5802b65b.png)
  
  Other companies not affected :thumbsup:
  
  Continue cleaning for the companys with more than 100 entries.
  Final Company unique count = 79
  Company Name | Count
  --- | --- 
  Amazon | 8238
  Microsoft | 5259
  Google      |        4368
  Facebook      |      2990
  Apple          |     2057
  Oracle          |    1143
  Salesforce     |     1065
  Intel           |     992
  Cisco            |    958
  IBM               |   927
  Uber            |     893
  Capital One      |    786
  LinkedIn         |    750
  VMware            |   682
  Qualcomm           |  578
  JPMorgan Chase      | 552
  Bloomberg      |      547
  Walmart         |     515
  Goldman Sachs    |    475
  PayPal            |   451
  Intuit             |  449
  Deloitte         |    434
  Nvidia           |    405
  Twitter          |    398
  Adobe            |    383
  SAP              |    368
  eBay             |    366
  Expedia          |   360
  Accenture        |    355
  Wayfair          |   339
  Lyft             |    326
  Netflix          |    268
  Workday          |    264
  Dropbox          |    254
  Dell             |    238
  Shopify          |    234
  Airbnb           |    229
  Visa             |    228
  Atlassian        |    219
  Snap             |    198
  Yelp             |    196
  Yahoo            |    189
  ServiceNow       |    189
  Tesla            |    179
  Square           |    176
  Zillow           |    175
  Stripe           |    173
  Yandex            |   170
  Indeed            |   170
  ByteDance          |  169
  Splunk       |        161
  EPAM       |          154
  Comcast     |         148
  Samsung       |       145
  T-Mobile       |      142
  Broadcom        |     142
  Spotify          |    141
  Nutanix           |   138
  Pinterest          |  137
  General Motors    |   134
  Autodesk          |   132
  American Express  |   131
  GoDaddy            |  130
  Morgan Stanley     |  129
  Boeing           |    128
  Ernst & Young   |     127
  Booking.com     |     127
  DoorDash         |    127
  Lockheed Martin   |   125
  AMD                |  122
  Qualtrics         |   118
  Cruise             |  117
  Instacart           | 116
  Twilio             |  116
  Disney             |  115
  Box                |  110
  PWC                 | 110
  Northrop Grumman   |  107
  Citi               |  104
  
  ### Cleaning Countries
  
  Issue:
  1. Inconsistency with data entries for 'USA'
  2. Considering countries with more than 100 entries
 
  Solution: Replace values and Filter len(x) >= 100
  
  ```sh
  df_company_100['Country'].replace(to_replace=['United States'], value = 'USA', inplace= True)
  
  df_company_100 = df_company_100.groupby('Country').filter(lambda x : len(x) >= 100)

  df_company_100.groupby(['Country'])['timestamp'].count()
  ```
  
  Output:
  
  ![image](https://user-images.githubusercontent.com/113367891/213167286-4e80d049-f5e7-4ba0-8bb3-d4174b561859.png)
    
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
