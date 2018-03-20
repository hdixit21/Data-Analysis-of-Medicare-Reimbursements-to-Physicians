# Data Analysis of Medicare Reimbursements to Physicians

## Objective
Analyze Medicare reimbursement payment information to physicians and observe any trends/patterns among the following factors:
* Physician Gender
* Physician Provider Type (i.e. Specialty)
* Physician Location (State/Region)
* Number of services provided
* Number of beneficiaries 
* Total Medicare Payment/Reimbursement Rate


## Problem Statement
Why Medicare reimbursement amounts differ drastically for physicians or healthcare professionals

## Questions to Answer
What physician demographics/characteristics are associated with higher Medicare payment amounts?

## Dataset
* [Physician and Other Supplier Data CY 2013](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Physician-and-Other-Supplier2013.html)
* Information on services and procedures provided to Medicare beneficiaries by physicians gathered by Centers for Medicare & Medicaid Services (CMS) for the year 2013
* Data includes physician demographic information, submitted charges, Medicare payment information, and beneficiary information
* We took a random sample of ≈ 60,000 entries
* We ensured the sample had an equal number of Female and Male physicians (≈ 30,000 each)

## Data Preparation and Cleaning
### Data filters used:
* We excluded gender-specific provider types (ex. OBGYN) or non-medical provider types (i.e. Social Worker)
* Average Age of Beneficiaries: 65 or older
* Physician who participates in Medicare only
* Mainland U.S. only
* Individuals only, not organizations (i.e. labs, hospitals, etc.)
Created ≈ 20 larger categories to generalize the 90+ provider types in the dataset for easier analysis
Categorized states into 5 geographic regions: north, south, southwest, midwest and west
Added columns for Average Income and Life Expectancy for each state in the dataset to see if any additional insights could be found

## Modeling Techniques Used
### CART and C5.0 Trees
Dataset had several categorical variables which we wanted to examine in relation to total Medicare payment amounts. Example: We categorized the Total Medicare Payment into Low, Medium and High and wanted to see how possible predictors (ie. gender, region, etc.) influenced these outcomes

### Kmeans Clustering
To group certain numerical values to determine if relationships existed. Also, better visualization of certain categorical predictors (ex. Gender, region)

### KNN
To predict the correlation between different attributes and find the accuracy between them

## CART and C5.0 Decision Trees
### Predictors Examined: 
* Gender
* State/Region
* Provider Type (i.e. Specialty)
* Average State Life Expectancy 

### Response Variables Examined: 
* Total Medicare Payments (continuous and categorical)
* Reimbursement Rate ( = Total Medicare Payment/Total Submitted Charges)

### Medicare payment categories:
* Low = $0-3000,000
* Medium = $300,000 – 500,000
* High = $500,000+

### CART – Provider Type and Reimbursement Rate
* Providers associated with higher rates of reimbursement: audiologists, nephrologists, optometrists and otolaryngologists
* Providers with lowest rates of reimbursement: Surgical providers, radiation, ER, anesthesiologists and gastroenterologists

