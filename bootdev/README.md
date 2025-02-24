An extensive document with useful notes about databases. 


# Contents:

-[Primary Keys](#primary-keys)

	Structured Query Language is the primary programming language used to manage and interact with relational databases.

Useful operators:

	- SELECT is the most common operator in SQL (often referred to as a "query")
	- ALTER is used to alter tables in our database. Often used to make changes without deletiong any data.



SQL Data Types

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

 <strong>Your Primary Key Will Almost Always Be the “id”</strong>>