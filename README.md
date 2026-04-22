# EDA USA Visa

This project explores U.S. permanent visa application data using exploratory data analysis (EDA) and basic preprocessing for later modeling.

## Dataset

The analysis uses the `us_perm_visas.csv` file included in this repository.

The dataset contains detailed PERM visa application records such as:
- application type
- case status
- decision date
- class of admission
- country of citizenship
- employer name, city, and state
- job title
- economic sector
- wage and prevailing wage fields
- worker education and related background details

Based on the filename, size, and column structure, this dataset appears to match the Kaggle dataset:
[US Permanent Visa Applications](https://www.kaggle.com/datasets/jboysen/us-perm-visas)

Source note:
The Kaggle page credits the original data to the U.S. Department of Labor.

## What Happens In The Notebook

The notebook starts by loading the CSV and checking the structure of the data.

Then it performs several cleaning steps, including:
- combining `case_no` and `case_number` into a single case identifier
- removing withdrawn applications
- merging `Certified-Expired` into `Certified`
- dropping fully empty rows and columns
- converting `decision_date` to datetime and extracting `year`
- standardizing text fields like `employer_city` and job titles
- keeping columns with stronger non-null coverage
- filling missing categorical values with mode
- cleaning `pw_soc_code`
- converting `pw_amount_9089` into numeric and filling missing values with median

After cleaning, the notebook explores trends such as:
- visa application status by year
- top employer cities
- top employers by number of applications
- U.S. economic sector distribution
- most common job titles
- case status by country of citizenship
- application type distribution
- foreign worker education levels

The notebook then prepares a smaller feature set, label-encodes selected categorical columns, and starts machine learning preparation.

## Purpose

The main goal of this project is to understand patterns in U.S. permanent visa applications and identify factors linked with certification and denial outcomes.

This helps answer questions like:
- how visa outcomes change over time
- which employers and cities appear most often
- which sectors and job roles dominate the applications
- how education, admission class, and work-related fields may relate to final visa decisions

## Files

- `6.EDA-US_VISA.ipynb` : notebook with EDA and preprocessing
- `us_perm_visas.csv` : dataset used in the analysis
