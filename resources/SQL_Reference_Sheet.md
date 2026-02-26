# SQL Reference Sheet for Beginners  
*(Adapted for Codecademy’s Learn SQL course)*  

A quick guide to help you understand the basic structure, syntax, and relationships used when working with **SQL** and **relational databases**.

---

## Understanding Databases

A **database** is an organized collection of related data stored in tables.  
**SQL (Structured Query Language)** is used to **create**, **read**, **update**, and **delete** data—often summarized as **CRUD** operations.

---

## Core Elements of a Database

| **Term** | **Definition** | **Example** |
|-----------|----------------|--------------|
| **Table** | A set of related data stored in rows and columns. Each table represents one type of information. | `customers` |
| **Column** | A field that defines an attribute for all rows in a table. | `email TEXT` |
| **Row** | A single record or entry in a table. | `(1, 'Ava', 'Perez', 'ava@example.com')` |
| **Primary Key (PK)** | A unique column that identifies each row. | `customer_id` |
| **Foreign Key (FK)** | A column that links data between tables. | `customer_id` in `orders` referencing `customers.customer_id` |
| **Constraint** | A rule that maintains data integrity. | `NOT NULL`, `UNIQUE`, `DEFAULT`, `CHECK`, `FOREIGN KEY` |

---

## Data Types

| **Data Type** | **Description** | **Example** |
|----------------|-----------------|--------------|
| **INTEGER** | A positive or negative whole number. | `age INTEGER` → `25` |
| **REAL** | A decimal or floating-point number. | `price REAL` → `19.99` |
| **TEXT** | A sequence of characters. | `name TEXT` → `'Ava Perez'` |
| **DATE** | A date formatted as `YYYY-MM-DD`. | `hire_date DATE` → `2026-02-26` |
| **BOOLEAN** | Stores `TRUE` or `FALSE` values. | `is_active BOOLEAN` → `TRUE` |

---

## Terminology

| **Term** | **Definition** | **Example** |
|-----------|----------------|--------------|
| **Clause** | A specific part of a SQL statement that performs a function. | In `SELECT * FROM customers WHERE age > 21;`, `FROM` and `WHERE` are clauses. |
| **Parameter** | A value used to filter or customize results in a query. | `WHERE name = 'Ava'` — `'Ava'` is a parameter. |
| **Alias** | A temporary name for columns or tables. | `SELECT name AS customer_name FROM customers;` |
| **Expression** | Combines columns, values, or operations to produce a result. | `price * quantity AS total_cost` |
| **Statement** | A complete SQL command that performs an action. | `SELECT * FROM customers;` |
| **Query** | A request to retrieve or modify data. | `SELECT * FROM orders;` |
| **Schema** | The layout or structure of a database. | A schema with `customers` and `orders` tables. |

---

## Common SQL Statements

| **Command / Clause** | **Purpose** | **Example** |
|-----------------------|-------------|--------------|
| **CREATE TABLE** | Defines a new table and its columns. | `CREATE TABLE customers (id INTEGER PRIMARY KEY, name TEXT);` |
| **INSERT INTO** | Adds one or more rows to a table. | `INSERT INTO customers (name, email) VALUES ('Ava Perez', 'ava@example.com');` |
| **SELECT** | Retrieves one or more columns from a table. | `SELECT name, email FROM customers;` |
| **\*** *(asterisk)* | A **wildcard** that selects **all columns** from a table. | `SELECT * FROM customers;` |
| **FROM** | Specifies which table to retrieve data from. | `SELECT * FROM customers;` |
| **WHERE** | Filters results based on a condition. | `SELECT * FROM customers WHERE name = 'Ava Perez';` |
| **ORDER BY** | Sorts query results by a column’s values. | `SELECT * FROM orders ORDER BY order_date DESC;` |
| **LIMIT** | Restricts how many rows are returned. | `SELECT * FROM customers LIMIT 5;` |
| **JOIN** | Combines rows from multiple tables using a shared column. | `SELECT * FROM customers JOIN orders ON customers.id = orders.customer_id;` |
| **UPDATE** | Changes existing data in a table. | `UPDATE customers SET email = 'new@example.com' WHERE id = 1;` |
| **DELETE FROM** | Removes rows from a table. | `DELETE FROM customers WHERE id = 5;` |
| **ALTER TABLE** | Modifies an existing table’s structure. | `ALTER TABLE customers ADD COLUMN phone TEXT;` |
| **ADD COLUMN** | Adds a new column to an existing table (used with `ALTER TABLE`). | `ALTER TABLE customers ADD COLUMN address TEXT;` |

---

## Example: Simple Database

### customers Table

| customer_id | name | email | date_of_birth |
|--------------|------|--------|----------------|
| 1 | Ava Perez | ava@example.com | 1994-03-12 |

### orders Table

| order_id | customer_id | order_date | total |
|-----------|--------------|-------------|--------|
| 501 | 1 | 2026-02-26 | 245.50 |

**Relationship:**  
`orders.customer_id` → references → `customers.customer_id`

---

## Helpful Tips for Beginners

- SQL statements are made up of **ordered clauses**:  
  `SELECT` → `FROM` → `WHERE` → `GROUP BY` → `HAVING` → `ORDER BY` → `LIMIT`
- Always **end statements with a semicolon (;)**
- Use **UPPERCASE** for SQL keywords and **lowercase** for names.
- The asterisk `*` returns all columns, but it’s better to specify only what you need.
- Be careful with `ALTER TABLE` and `DELETE` — they permanently change data.
- Practice writing and testing small queries often.  

---

### Disclaimer  
This reference sheet is for **educational purposes only**, adapted from materials in **Codecademy’s Learn SQL** course.
