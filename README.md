
# Employee Salary Analysis using SQL

This repository contains SQL queries and scripts used to analyze employee salary data from the **San Francisco City Employee Salaries Dataset** (2011-2014). The dataset is publicly available on [Kaggle](https://www.kaggle.com/datasets/kaggle/sf-salaries) and includes information about job titles, base pay, overtime pay, total pay, and benefits for city employees.

## Dataset Description

The **SF Salaries Dataset** provides detailed information on employee compensation for public employees in San Francisco. It covers salary components like:
- Base Pay
- Overtime Pay
- Other Pay (additional compensations)
- Total Pay (sum of base, overtime, and other pay)
- Total Pay Benefits (total pay including benefits)

The dataset has been used to run various queries for data analysis, including identifying the highest-paid employees, calculating average pay, and performing updates and deletions based on specific conditions.

You can explore the dataset on Kaggle via [this link](https://www.kaggle.com/datasets/kaggle/sf-salaries).

## SQL Queries Overview

This project contains the following types of queries:

1. **Basic Select Queries**: Retrieve data, including employee names, job titles, and salary components.
2. **Aggregations**: Compute average, maximum, and count values for salary-related data.
3. **Filtering Data**: Use conditions to filter employees based on their job titles, overtime pay, and total compensation.
4. **Data Modifications**: Update and delete data, such as increasing base pay for managers by 10% or removing employees without overtime pay.
5. **Ordering and Grouping**: Sort data based on total pay benefits and group job titles by average pay.

## Sample SQL Queries

```sql
-- Show all columns and rows in the table.
SELECT * FROM salaries;

-- Show the average base pay for all employees.
SELECT AVG(BasePay) AS "Avg BasePay" FROM salaries;

-- Show the top 10 highest-paid employees.
SELECT EmployeeName, TotalPay FROM salaries
ORDER BY TotalPay DESC
LIMIT 10;

-- Update base pay for employees with "Manager" in their job title.
UPDATE salaries
SET BasePay = BasePay * 1.1
WHERE JobTitle LIKE "%Manager%";

-- Delete all employees with no overtime pay.
DELETE FROM salaries
WHERE OvertimePay = 0;
```

## Instructions for Use

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/employee-salary-sql.git
    ```
2. Ensure you have the required dataset, which can be downloaded from [Kaggle](https://www.kaggle.com/datasets/kaggle/sf-salaries).
3. Import the dataset into your SQL environment (MySQL, PostgreSQL, etc.).
4. Run the SQL queries provided in the `queries.sql` file.

## License

This project is open-source under the MIT License. Feel free to contribute or suggest improvements.

---

You can copy this content into your `README.md` file, and it will serve as documentation for your project. The SQL code can be saved in a separate `.sql` file, like `queries.sql`, for easier access.
