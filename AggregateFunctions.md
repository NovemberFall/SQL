### Count Functions

![](img/2019-10-07-20-12-16.png)
---
![](img/2019-10-07-20-12-28.png)
---
![](img/2019-10-07-20-16-15.png)
---
- count distinct
![](img/2019-10-07-20-17-38.png)
---
- last name
![](img/2019-10-07-20-20-21.png)
---
- distinct last name
![](img/2019-10-07-20-26-10.png)
---
- select first name and last name
![](img/2019-10-07-20-28-34.png)
---
- distinct first name and last name
![](img/2019-10-07-20-30-52.png)
---
- How many titles contain "the"?
![](img/2019-10-07-20-32-34.png)
---
![](img/2019-10-07-20-33-11.png)

```sql
SELECT COUNT(*) FROM books;
 
SELECT COUNT(author_fname) FROM books;
 
SELECT COUNT(DISTINCT author_fname) FROM books;
 
SELECT COUNT(DISTINCT author_lname) FROM books;
 
SELECT COUNT(DISTINCT author_lname, author_fname) FROM books;
 
SELECT title FROM books WHERE title LIKE '%the%';
 
SELECT COUNT(*) FROM books WHERE title LIKE '%the%';
```