# Databases

Database systems notes.

## Normalization

> Normalization is the process of organizing a Data Object into tables, rows and columns.

There are several levels of normalization.


### First normal form (1NF)

> This is the minimum requirement for a relational database.

* It eliminates repeating groups in individual tables.
* Create a separate table for each set of related data.
* Identify each set of related data with a primary key.



### Second normal form (2NF)

* It complies with **1NF**
* All the non-key attributes should be dependent on a key.
* If there is a key that has no relationship or is unnecessary, it should be pulled out into another table.


### Third normal form (3NF)

> Reduces redundancy 

* It complies with **2NF**
* Split the table as much as possible. Prefer leaving keys instead of values.



## Database as a Service

- EventStore-based database - https://geteventstore.com/
- AWS RDS