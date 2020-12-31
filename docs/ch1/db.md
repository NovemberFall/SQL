## Create/Drop Database/Table

### creating databases

- List available databases:
- `show databases; `
- The general command for creating a database:
- `CREATE DATABASE database_name; `
- A specific example:
- `CREATE DATABASE soap_store; `

---
### Dropping Data

- `DROP DATABASE testing_db;`

---

### using Databases

- if we wanted to know for sure what database we are currently using

- `SELECT database();`


![](img/2019-09-30-21-55-00.png)

---

![](img/2019-09-30-21-57-26.png)

---

### The Basic Datatypes

![](img/2019-09-30-22-04-18.png)

---

![](img/2019-09-30-22-14-46.png)

---

```sql
CREATE TABLE tablename
  (
    column_name data_type,
    column_name data_type
  );
CREATE TABLE cats
  (
    name VARCHAR(100),
    age INT
  );
```

---

```sql
SHOW TABLES;
 
SHOW COLUMNS FROM tablename;
 
DESC tablename;
```

![](img/2019-10-01-08-26-16.png)

---



### Dropping tables

```sql
-- Dropping Tables
DROP TABLE <tablename>; 

-- A specific example:

DROP TABLE cats; 
```

![](img/2019-10-01-08-28-18.png)

---

- Creating tables

```sql
CREATE TABLE pastries
  (
    name VARCHAR(50),
    quantity INT
  );
 
SHOW TABLES;
 
DESC pastries;
 
DROP TABLE pastries;
```

![](img/2019-10-01-09-22-05.png)

