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
