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
