## 595. Big Countries
![](img/2022-10-08-15-12-26.png)

```sql
# Write your MySQL query statement below
SELECT name, population, area
FROM World
WHERE area >= 3000000 OR population >= 25000000
```