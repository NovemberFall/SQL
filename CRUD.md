### Introduction to CURD
- CREATE
- READ
- UPDATE
- DELETE
---

### preparing DATA
- ` DROP TABLE CATS;`
---
![](img/2019-10-04-16-10-54.png)
---
- insert new data
```sql
INSERT INTO cats(name, breed, age) 
VALUES ('Ringo', 'Tabby', 4),
       ('Cindy', 'Maine Coon', 10),
       ('Dumbledore', 'Maine Coon', 11),
       ('Egg', 'Persian', 4),
       ('Misty', 'Tabby', 13),
       ('George Michael', 'Ragdoll', 9),
       ('Jackson', 'Sphynx', 7);
```
---
### introduction SELECT
![](img/2019-10-04-16-13-52.png)
---
```sql
SELECT * FROM cats; 

SELECT name FROM cats; 

SELECT age FROM cats; 

SELECT cat_id FROM cats; 

SELECT name, age FROM cats; 

SELECT cat_id, name, age FROM cats; 

SELECT age, breed, name, cat_id FROM cats; 

SELECT cat_id, name, age, breed FROM cats; 
```
![](img/2019-10-04-16-38-41.png)
---
![](img/2019-10-04-16-38-55.png)
---
![](img/2019-10-04-16-39-08.png)
---

---
### Introduction WHERE
![](img/2019-10-04-16-42-08.png)
---

### SELECT Challenges
```sql
-- CODE: Select Challenges Solution
SELECT cat_id FROM cats; 

SELECT name, breed FROM cats; 

SELECT name, age FROM cats WHERE breed='Tabby'; 

SELECT cat_id, age FROM cats WHERE cat_id=age; 

SELECT * FROM cats WHERE cat_id=age; 
```

---
### Introduction to Aliases
- `SELECT cat_id AS id, name FROM cats;`
![](img/2019-10-04-16-48-44.png)
---
- `SELECT name AS 'cat name', breed AS 'kitty breed' FROM cats;`
![](img/2019-10-04-16-50-00.png)
---

### Upadate 
```sql
-- Change tabby cats to shorthair:

UPDATE cats SET breed='Shorthair' WHERE breed='Tabby'; 

-- Another update:

UPDATE cats SET age=14 WHERE name='Misty'; 
```
![](img/2019-10-04-16-57-07.png)
---

### Update Challenge
![](img/2019-10-04-16-59-25.png)
---
![](img/2019-10-04-17-00-49.png)
---
![](img/2019-10-04-17-02-59.png)
---
```sql
SELECT * FROM cats WHERE name='Jackson';
 
UPDATE cats SET name='Jack' WHERE name='Jackson';
 
SELECT * FROM cats WHERE name='Jackson';
 
SELECT * FROM cats WHERE name='Jack';
 
SELECT * FROM cats WHERE name='Ringo';
 
UPDATE cats SET breed='British Shorthair' WHERE name='Ringo';
 
SELECT * FROM cats WHERE name='Ringo';
 
SELECT * FROM cats;
 
SELECT * FROM cats WHERE breed='Maine Coon';
 
UPDATE cats SET age=12 WHERE breed='Maine Coon';
 
SELECT * FROM cats WHERE breed='Maine Coon';
```
---

### Introduction to DELETE
```sql
DELETE FROM cats WHERE name='Egg';
 
SELECT * FROM cats;
 
SELECT * FROM cats WHERE name='egg';
 
DELETE FROM cats WHERE name='egg';
 
SELECT * FROM cats;
 
DELETE FROM cats;
```
---
![](img/2019-10-04-17-07-02.png)
---
![](img/2019-10-04-17-07-16.png)
---

### DELETE Challenges
```sql
SELECT * FROM cats WHERE age=4;
 
DELETE FROM cats WHERE age=4;
 
SELECT * FROM cats WHERE age=4;
 
SELECT * FROM cats;
 
SELECT *  FROM cats WHERE cat_id=age;
 
DELETE FROM cats WHERE cat_id=age;
 
DELETE FROM cats;
 
SELECT * FROM cats;
```
---

### CRUD Challenge
![](img/2019-10-04-17-10-25.png)
---
