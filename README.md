# CDE-Bootcamp
## Your manager has assigned you the task of building a Bash script (use only Bash scripting) that performs a simple ETL process

ETL, or Extract, Transform, Load, is a necessary data engineering process, that involves extracting data from various sources, converting it into a workable form, and moving it to some destination, such as a database. ETL pipelines automate this process, ensuring that data is processed consistently and efficiently, providing a framework for tasks like data analysis, reporting, and machine learning, and ensuring data is clean, reliable, and ready to use.

# For the ETL, I used these specific command line tools:
- mkdir
- cd
- curl
- jq
- awk
- sed

# Setting up a working directory
I set up a dedicated directory 'raw' folder as requested in the assignment 
- mkdir raw
- cd raw

# Extracting Data
I used curl to fetch data from this [Link](https://www.stats.govt.nz/assets/Uploads/Annual-enterprise-survey/Annual-enterprise-survey-2023-financial-year-provisional/Download-data/annual-enterprise-survey-2023-financial-year-provisional.csv)

- curl -o data.csv "(https://www.stats.govt.nz/assets/Uploads/Annual-enterprise-survey/Annual-enterprise-survey-2023-financial-year-provisional/Download-data/annual-enterprise-survey-2023-financial-year-provisional.csv)"

# Transforming Data
- Renaming the column named Variable_code to variable_code.
    - nano data.csv
- selected only the following columns: year, Value, Units, and variable_code.
    - awk -F, '{print $1, $5, $6, $9}' data.csv >  2023_year_finance.csv
- Saving the content of these selected columns into a file named 2023_year_finance.csv.
- The file was saved in a folder called 'Transformed'

# Load
Loaded the transformed data into a directory named "Gold"
mkdir Gold 
mv 2023_year_finance.csv Gold











