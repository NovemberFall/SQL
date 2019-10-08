- Inserting Data

```sql
-- The "formula":

INSERT INTO table_name(column_name) VALUES (data);

-- For example:
INSERT INTO cats(name, age) VALUES ('Jetson', 7);
```
![](img/2019-10-01-09-38-16.png)
---

---
### Intro to SELECT
- `SELECT * FROM cats`
![](img/2019-10-03-10-44-18.png)
---


---
### Multiple INSERT
![](img/2019-10-03-10-48-45.png)
```sql
INSERT INTO table_name 
            (column_name, column_name) 
VALUES      (value, value), 
            (value, value), 
            (value, value);
```
---

### INSERT challenges

#### create a people table
- first_name - 20 char limit
- last_name - 20 char limit
- age

If you're wondering how to insert a string (VARCHAR) value that contains quotations, then here's how.

You can do it a couple of ways:
- Escape the quotes with a backslash: 
- `"This text has \"quotes\" in it"` or
- `'This text has \'quotes\' in it'`
---

```sql
CREATE TABLE people
  (
    first_name VARCHAR(20),
    last_name VARCHAR(20),
    age INT
  );
INSERT INTO people(first_name, last_name, age)
VALUES ('Tina', 'Belcher', 13);
INSERT INTO people(age, last_name, first_name)
VALUES (42, 'Belcher', 'Bob');
INSERT INTO people(first_name, last_name, age)
VALUES('Linda', 'Belcher', 45),
      ('Phillip', 'Frond', 38),
      ('Calvin', 'Fischoeder', 70);
```

```sql
DROP TABLE people; 

SELECT * FROM people; 

show tables; 
```
![](img/2019-10-03-23-04-26.png)
---
![](img/2019-10-03-23-04-48.png)
---

### MySQL Warnings
---

### Null Not Null

- Null means the value is not known
- Don't mean zero !
![](img/2019-10-04-09-10-00.png)
---

- this time create a table with NOT NULL
![](img/2019-10-04-09-11-36.png)
---

- CODE: NULL and NOT NULL
```sql
-- Try inserting a cat without an age:

INSERT INTO cats(name) VALUES('Alabama'); 

SELECT * FROM cats; 

-- Try inserting a nameless and ageless cat:

INSERT INTO cats() VALUES(); 


-- Define a new cats2 table with NOT NULL constraints:
```
---

### To Set Default Values
![](img/2019-10-04-09-33-07.png)
---
![](img/2019-10-04-09-33-26.png)
---

- `INSERT INTO cats3(age) VALUES(13);`
![](img/2019-10-04-09-37-34.png)
---
![](img/2019-10-04-09-38-24.png)
- we have another unnamed cat
```sql
CREATE TABLE cats3
  (
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99
  );

-- Notice the change when you describe the table:

DESC cats3; 

-- Insert a cat without a name:

INSERT INTO cats3(age) VALUES(13); 

-- Or a nameless, ageless cat:

INSERT INTO cats3() VALUES(); 

-- Combine NOT NULL and DEFAULT:
CREATE TABLE cats4
  (
    name VARCHAR(20) NOT NULL DEFAULT 'unnamed',
    age INT NOT NULL DEFAULT 99
  );

-- Notice The Difference:
INSERT INTO cats() VALUES();
 
SELECT * FROM cats;
 
INSERT INTO cats3() VALUES();
 
SELECT * FROM cats3;
 
INSERT INTO cats3(name, age) VALUES('Montana', NULL);
 
SELECT * FROM cats3;
 
INSERT INTO cats4(name, age) VALUES('Cali', NULL);
```

---
### A Primer On Primary keys
![](img/2019-10-04-10-09-20.png)
---
- if we repeatly added 6 entities
![](img/2019-10-04-10-10-11.png)
---
![](img/2019-10-04-10-10-39.png)
- so how do we make each Unique?
- Primary Key, A Unique Identifier
![](img/2019-10-04-10-13-45.png)
---
- how do we know the primary key?
![](img/2019-10-04-10-16-43.png)
---
- what if we add id still equals 1?
![](img/2019-10-04-10-17-45.png)
---
- AUTO_INCREMENT
```sql
 CREATE TABLE unique_cats2( 
   cat_id INT NOT NULL AUTO_INCREMENT, 
   name VARCHAR(100), 
   age INT, 
   PRIMARY KEY (cat_id) 
  );
```
![](img/2019-10-04-10-40-31.png)
---
![](img/2019-10-04-10-43-53.png)
---
![](img/2019-10-04-10-44-06.png)
---

- source codes
```sql
-- CODE: Primary Keys
-- Define a table with a PRIMARY KEY constraint:

CREATE TABLE unique_cats
  (
    cat_id INT NOT NULL,
    name VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
  );
DESC unique_cats; 

-- Insert some new cats:

INSERT INTO unique_cats(cat_id, name, age) VALUES(1, 'Fred', 23);
 
INSERT INTO unique_cats(cat_id, name, age) VALUES(2, 'Louise', 3);
 
INSERT INTO unique_cats(cat_id, name, age) VALUES(1, 'James', 3);
-- Notice what happens:

SELECT * FROM unique_cats; 

-- Adding in AUTO_INCREMENT:

CREATE TABLE unique_cats2 (
    cat_id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
);
INSERT a couple new cats:

INSERT INTO unique_cats2(name, age) VALUES('Skippy', 4);
INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);
INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);
INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);
INSERT INTO unique_cats2(name, age) VALUES('Skippy', 4);
-- Notice the difference:

SELECT * FROM unique_cats2; 
```
---
### Table Constraints Exercise
```sql
USE test;
CREATE TABLE employees( 
    id INT AUTO_INCREMENT NOT NULL,
    first_name VARCHAR(225) NOT NULL,
    last_name VARCHAR(225) NOT NULL,
    middle_name VARCHAR(225),
    age INT NOT NULL,
    current_status VARCHAR(225) NOT NULL DEFAULT 'employed',
	PRIMARY KEY(id) 
);
```
![](img/2019-10-04-15-43-10.png)
---
- `INSERT INTO employees(first_name, last_name, age) VALUES('Dora','Smith',58);`
![](img/2019-10-04-15-46-24.png)
---
- Another way of defining a primary key:
```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    middle_name VARCHAR(255),
    age INT NOT NULL,
    current_status VARCHAR(255) NOT NULL DEFAULT 'employed'
);

-- A test INSERT:

INSERT INTO employees(first_name, last_name, age) VALUES
('Dora', 'Smith', 58);
```



