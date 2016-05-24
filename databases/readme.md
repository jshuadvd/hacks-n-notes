# Databases

Database systems notes.

## Normalization

> Normalization is the process of organizing a Data Object into tables, rows and columns.

There are several levels of normalization.

The more you normalize it will be more DRY, but it will be harder to understand and would slow performance. It is an equivalent to creating abstractions.

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

## “Object-Relational Impedance Mismatch”

To work with relational tables you need to JOIN, and with Objects you need to traverse. There is a mismatch in the shapes of the Relational vs Objects.

## Database as a Service

- EventStore-based database - https://geteventstore.com/
- AWS RDS

## Migrator

> Use a migrator tool or pattern to keep the db in good shape.

* Each time there is a change in the structure of the database (eg. create a table, delete a column, etc) you should append the command in a historic of SQL commands.
* Enumerate all the commands
* Run through all the commands
* Save the index number of the last command executed.
* Next time you run the migrator, it should start running from the last command that it previously ran.
* This will ensure that you aren't running commands that don't need to be executed.
