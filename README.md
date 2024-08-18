
---

# Crowdfunding ETL Pipeline Project

## Overview
This project involves building an ETL (Extract, Transform, Load) pipeline to process crowdfunding data. The project is designed to give hands-on experience in data extraction, transformation, and loading into a PostgreSQL database. The project is completed in collaboration with a partner, utilizing Python, Pandas, and either dictionary methods or regular expressions for data manipulation.

## Table of Contents
- [Overview](#overview)
- [Project Description](#project-description)
- [Project Structure](#project-structure)
- [Instructions](#instructions)
- [Installation](#installation)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## Project Description
The goal of this project is to:
1. Extract data from provided Excel files (`crowdfunding.xlsx` and `contacts.xlsx`).
2. Transform the extracted data into meaningful formats:
   - Create category and subcategory DataFrames.
   - Create a campaign DataFrame.
   - Create a contacts DataFrame.
3. Load the transformed data into a PostgreSQL database.

This process involves creating four CSV files from the transformed data and defining a relational database schema, which is implemented in PostgreSQL.

## Project Structure
The repository is organized as follows:

```
Crowdfunding_ETL/
│
├── Resources/
│   ├── crowdfunding.xlsx
│   ├── contacts.xlsx
│   ├── category.csv
│   ├── subcategory.csv
│   ├── campaign.csv
│   └── contacts.csv
│
├── ETL_Mini_Project_YourInitials_PartnerInitials.ipynb
├── README.md
└── crowdfunding_db_schema.sql
```

## Instructions
The project is divided into the following steps:

### 1. Create the Category and Subcategory DataFrames
- Extract and transform data from `crowdfunding.xlsx` to create the `category` and `subcategory` DataFrames.
- Save the DataFrames as `category.csv` and `subcategory.csv`.

### 2. Create the Campaign DataFrame
- Extract and transform data from `crowdfunding.xlsx` to create the `campaign` DataFrame.
- Save the DataFrame as `campaign.csv`.

### 3. Create the Contacts DataFrame
- Extract and transform data from `contacts.xlsx` using either Python dictionary methods or regular expressions.
- Split the `name` column into `first_name` and `last_name`.
- Save the DataFrame as `contacts.csv`.

### 4. Create the Crowdfunding Database
- Design the database schema based on the DataFrames created.
- Implement the schema in a PostgreSQL database.
- Load the CSV files into the corresponding tables.
- Verify data integrity by running SELECT statements.

## Installation
To run the project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/maslla100/Crowdfunding_ETL
    ```
2. Navigate to the project directory:
    ```bash
    cd Crowdfunding_ETL
    ```
3. Install the required Python packages:
    ```bash
    pip install pandas psycopg2
    ```
4. Ensure you have PostgreSQL installed and running on your machine.
5. Set up your PostgreSQL database and create the tables using the provided schema (`crowdfunding_db_schema.sql`).

## Database Schema
The database schema consists of the following tables:

1. **category**
    - category_id (Primary Key)
    - category
2. **subcategory**
    - subcategory_id (Primary Key)
    - subcategory
3. **campaign**
    - cf_id (Primary Key)
    - contact_id (Foreign Key)
    - company_name
    - description
    - goal (Float)
    - pledged (Float)
    - outcome
    - backers_count
    - country
    - currency
    - launch_date (Datetime)
    - end_date (Datetime)
    - category_id (Foreign Key)
    - subcategory_id (Foreign Key)
4. **contacts**
    - contact_id (Primary Key)
    - first_name
    - last_name
    - email

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## License
This project is licensed under the MIT License.

---
