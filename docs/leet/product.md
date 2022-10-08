## 1757. Recyclable and Low Fat Products
![](img/2022-10-08-15-14-04.png)

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y'
```