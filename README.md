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

![reimbursement rate and specialty](https://user-images.githubusercontent.com/37488697/37632249-bb8c0d22-2bc3-11e8-822c-d54e6fab6b49.jpg)

### CART – Provider Type and Total Payment 
* Providers with the highest total Medicare payment amounts: Oncologists, Hematologists, Rheumatologists & Optometrists
* This may be due to elderly patients often suffering from joint and eye problems, as well as cancer

### CART and C5.0 – Gender and Total Payment 
* Male physicians were associated with higher Medicare reimbursements than Female physicians
* The median Medicare payment for Female physicians was $154,466, compared to $498,569  for males(over 3X as much)
* This can be due to the fact that men outnumbered women in all the specialties associated with the highest reimbursement amounts (i.e. optometry, oncology), while more women were in specialties with the lowest reimbursement amounts (i.e. therapy)

### Kmeans – Gender and Total Payment 
This conclusion was also supported by clustering total Medicare payments by each gender

### CART and C5.0 – State/Region and Total Payment
* Higher Medicare payment totals were associated with south, southwest and west regions
* Florida was the state with the highest Medicare reimbursement totals
* Not surprisingly, Florida has the greatest proportion of people who are at least 65, according to the U.S. Census Bureau

### Kmeans Clustering – Region and Total Payment
This conclusion was supported by clustering the total Medicare payments for the 5 regions using Kmeans


### CART– Number of Services,  Number of Beneficiaries and Total Payment
* There was also a relationship between the number of services a physician provided and the total Medicare payment amount - Higher payments were associated with a higher number of services
* Similarly, higher payments were associated with a higher number of beneficiaries

### CART – Average Life Expectancy and Reimbursement Rate 
Highest rates of Medicare reimbursements seemed to be associated with higher state average life expectancies

### Kmeans – Total Submitted Charges and Total Payment
Total Submitted Charges by physicians seemed to have an almost linear relationship to the Total Amount Medicare actually reimbursed - Higher submitted charges were associated with higher Medicare payments


## C5.0 Decision Trees 

### C5.0 - Multiple Predictors

#### Gender + Region:
Highest Medicare reimbursement was among Males in southern and western regions
Females were associated with the lowest reimbursement among all regions

#### Gender + Specialty:
For male physicians: oncology, hematology, dermatology, optometry and rheumatology had the highest reimbursement
For female physicians: oncology, hematology, rheumatology had the highest reimbursement

## Conclusions
* Two most important predictors for Total Medicare Payment:
  - Gender
  - Specialty
  - State/Region had less of an influence

## Significance/Future Work:
* Can be used to find what kinds of services/specialties are most used/needed by seniors
  - Compare to historical data to see what specialties had the highest increase in number of services/beneficiaries
* Can show varying reimbursement rates/amounts among different specialties or areas, perhaps indicating a need for reevaluation/examination by Medicare
