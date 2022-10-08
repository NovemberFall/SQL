## 584. Find Customer Referee
![](img/2022-10-08-15-22-00.png)

```sql
SELECT name
FROM Customer
WHERE referee_id != 2 OR referee_id is null
```

- don't type `referee_id = null`