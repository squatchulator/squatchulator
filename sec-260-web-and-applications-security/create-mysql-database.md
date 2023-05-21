---
description: 4/17/2023
---

# Create MySQL Database

### Log into MySQL server using login from last lab:

* `mysql -u root -p`

### Show existing databases:

* `SHOW DATABASES;`

### Create a new database:

* `CREATE DATABASE pets;`

### Create a table inside the database:

* Select table with `USE pets`
* `CREATE TABLE cats`
* `(`
* `id INT unsigned NOT NULL AUTO_INCREMENT, # Unique ID for the record`
* `name VARCHAR(150) NOT NULL, # Name of the cat`
* `owner VARCHAR(150) NOT NULL, # Owner of the cat`
* `birth DATE NOT NULL, # Birthday of the cat`
* `PRIMARY KEY (id) # Make the id the primary key`
* `);`

### See information on all columns of a table:

* `DESCRIBE cats;`

### Adding records to a table:

* `INSERT INTO cats ( name, owner, birth) VALUES`
* `( 'Siggy', 'Harold', '2018-01-05' ),`
* `( 'Freya', 'Gutenber', '2017-11-10' ),`
* `( 'Patches', 'Charlie', '2015-05-15' );`

### Retrieve records from a table:

* `SELECT * FROM cats;`

### Select specific columns and rows by a certain condition:

* `SELECT name FROM cats WHERE owner = 'Charlie';`

### Deleting a record from a table:

* `DELETE FROM cats WHERE name='Freya';`

### Adding or deleting a column from a table:

* `ALTER TABLE cats ADD gender CHAR(1) AFTER name;`
* `ALTER TABLE cats DROP gender;`

### View details of table:

* `SHOW CREATE TABLE cats\G`
