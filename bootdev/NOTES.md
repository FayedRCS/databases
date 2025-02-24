An extensive document with useful notes about databases. 


# Contents:

-[Primary Keys](#primary-keys)

-[Foreign Keys](#foreign-keys)

-[Schema](#schema)

-[Relational Databases](#relational-databases)


---------------------
Structured Query Language is the primary programming language used to manage and interact with relational databases.

### Useful operators:

	- SELECT is the most common operator in SQL (often referred to as a "query")
	- ALTER is used to alter tables in our database. Often used to make changes without deletiong any data.



### SQL Data Types

	SQl as a language can support many different data types. However, the datatypes that <strong>your</strong> database management system (DBMS) supports will vary depending on the specific database you're using.   



SQLite tidbits

SQLite Data Type:
	
	1. NULL - Null value.
	2. INTEGER - A signed integer stored in 0,1,2,3,4,6, or 8 bytes.
	3. REAL - Floating point value stored as an 64-bit IEEE floating point number.
	4. TEXT - Text string stored using database encoding such as UTF-8
	5. BLOB - Short for Binary large object and typically used for images, audio or other multimedia.
	6. BOOLEAN - Boolean values are written in SQLite queries as true or false, but are recorded as 1 or 0.



## Primary keys

 A key defines and protects relationships between tables. A primary key is a special column that uniquely identifies records within a table. Each table can have one, and only one primary key.

 <strong>Your Primary Key Will Almost Always Be the “id”</strong>



 ## Foreign keys

 Foreign keys are what makes relational databases relational! Foreign keys define the relationships between tables. Simply put, a FOREIGN KEY is a field in one table that references another table's PRIMARY KEY.

 ### In SQLite

 Creating a FOREIGN KEY in SQLite happens at table creation! After we define the table fields and constraints we add a named CONSTRAINT where we define the FOREIGN KEY column and its REFERENCES:

 ```
 CREATE TABLE departments (
    id INTEGER PRIMARY KEY,
    department_name TEXT NOT NULL
);

CREATE TABLE employees (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    department_id INTEGER,
    CONSTRAINT fk_departments
    FOREIGN KEY (department_id)
    REFERENCES departments(id)
);

```


NOTE:

In this example, an employee has a department_id. The department_id must be the same as the id field of a record from the departments table. fk_departments is the specified name of the constraint.

CONSTRAINT fk_departments: create a constraint called fk_departments

FOREIGN KEY (department_id): make this constraint a foreign key assigned to the department_id field

REFERENCES departments(id): link the foreign field id from the departments table


## Schema 

A database's schema describes how data is organized within it.

Data types, table names, field names, constraints, and the relationships between all of those entities are part of a database's schema.

# Relational Databases

A relational database is a type of database that stores data so that it can be easily related to other data.

In a relational database:

1. Data is typically represented in "tables".

2. Each table has "columns" or "fields" that hold attributes related to the record.

3. Each row or entry in the table is called a record.

4. Typically, each record has a unique Id called the primary key.

The big difference between relational and non-relational databases is that non-relational databases nest their data. Instead of keeping records on separate tables, they store records within other records. This often results in duplicate data within the database.