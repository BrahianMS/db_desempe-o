# 

## Project Description
This system allows loading and managing data in a MySQL database through bulk CSV uploads.  
It supports files with different structures and automatically adapts column mapping to the database table.  
Additionally, the project includes advanced SQL queries, a normalized database model and a crud of one of the entities.

---

## How to Run the Project

### Load CSV
1. **Install dependencies**

```bash
npm i fs csv-parser mysql2
```

2. **Configure the database connection**
Edit the config.js or connection section in the .js file with your MySQL credentials:

```javascript
const connection = mysql.createConnection({
host: 'localhost',
user: 'root',
password: 'your_password',
database: 'your_database'
});
```

3. **Run the bulk upload script**

```bash
node upload.js
```

### Run the database system
1. **Install dependencies**
At './backend'

```bash
npm i express mysql2 
```

2. **Configure the database connection**
Edit the config.js or connection section in the .js file with your MySQL credentials:

```javascript
const connection = mysql.createConnection({
host: 'localhost',
user: 'root',
password: 'your_password',
database: 'your_database'
});
```

3. **Run the express server**

```bash
node app.js
```

### Crud
For the crud, just open the home.html file at '.frontend'.


## Technologies Used
- Node.js

- MySQL

- CSV Parser

- JavaScript

- Express

## Database Normalization
The database follows Third Normal Form (3NF) to:

Eliminate redundant data.

Ensure data integrity.

Facilitate advanced queries.

## Bulk Upload from CSV
Place your .csv files in the csv_folder/ directory.

File names must match the table name in MySQL (e.g., users.csv → users table).

Run:

```bash
node upload.js
```
The system will:

Read all .csv files in the folder.

Insert or update records dynamically.

Log any errors found during processing.

## Advanced Queries Explanation
This project includes advanced SQL queries such as:

Total payment by each customer

Information of pending bills

Nequi and Daviplata platform's transactions


Example:

```sql
SELECT  c.id AS customer_id, c.name AS customer_name, SUM(t.amount) AS total_paid
FROM customers c 
JOIN transactions t ON c.id = t.id_customer
GROUP BY c.id, c.name;
```

## Relational Model Screenshot

At './modelo.png'

## Developer Information
Name: John Brahian Montoya Serna

Clan: Van Rossum

Email: johnbra696@gmail.com