
# Schemas and relationships
### What is a schema and why/when would you need one?

A schema is the organisation and structure of a database
It contains objects like tables, columns, data types, views, stored procedures, relationships, primary keys, foreign keys, etc.
It can be represented in a visual design which shows the database objects and their relationship with each other in a schema diagram

---

### What are primary keys and why do we need them?

A **primary key** is a field in a table which uniquely identifies each row/record in a database table, and provides a way for developers to reference a particular row within a database table.
Primary keys must contain unique values.
A primary key column cannot have NULL values.

```
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
PRIMARY KEY (ID)
);
```

OR 

```
CREATE TABLE Persons (
ID int NOT NULL PRIMARY KEY,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int
);
```

---

### Create a visual representation of a mock schema for a database about Founders & Coders, using as many different kinds of relationship as you can. Explain the logic behind it.

<p align="center">
<img src="https://raw.githubusercontent.com/FAC10/research/master/week-6/schema-example-oracle.png">
</p>

---

### By :
 > * Marwan  
 > * Asmaa
 > * Ons
