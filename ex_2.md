# Exercise 2

## ex_1

寫出可以得到下方結果的 SQL 語句

Answer

```sql
SELECT 
	m.member_id, 
	m.name AS member, 
	c.committee_id, 
	c.name AS committee
FROM members m
INNER JOIN committees c
ON m.name = c.name;
```

Output

```
+-----------+--------+--------------+-----------+
| member_id | member | committee_id | committee |
+-----------+--------+--------------+-----------+
|         1 | John   |            1 | John      |
|         3 | Mary   |            2 | Mary      |
|         5 | Amelia |            3 | Amelia    |
+-----------+--------+--------------+-----------+
3 rows in set (0.00 sec)
```

## ex_2

寫出可以得到下方結果的 SQL 語句

Answer

```sql
SELECT 
	m.member_id, 
	m.name AS member, 
	c.committee_id, 
	c.name AS committee
FROM members m
LEFT OUTER JOIN committees c
ON m.name = c.name;
```

Output

```
+-----------+--------+--------------+-----------+
| member_id | member | committee_id | committee |
+-----------+--------+--------------+-----------+
|         1 | John   |            1 | John      |
|         2 | Jane   |         NULL | NULL      |
|         3 | Mary   |            2 | Mary      |
|         4 | David  |         NULL | NULL      |
|         5 | Amelia |            3 | Amelia    |
+-----------+--------+--------------+-----------+
5 rows in set (0.00 sec)
```

## ex_3

寫出可以得到下方結果的 SQL 語句

Answer

```sql
SELECT 
	m.member_id, 
	m.name AS member, 
	c.committee_id, 
	c.name AS committee
FROM members m
LEFT OUTER JOIN committees c
ON m.name = c.name
WHERE c.committee_id IS NULL;
```

Output

```
+-----------+--------+--------------+-----------+
| member_id | member | committee_id | committee |
+-----------+--------+--------------+-----------+
|         2 | Jane   |         NULL | NULL      |
|         4 | David  |         NULL | NULL      |
+-----------+--------+--------------+-----------+
2 rows in set (0.00 sec)
```

## ex_4

寫出可以得到下方結果的 SQL 語句

Answer

```sql
SELECT 
	m.member_id, 
	m.name AS member, 
	c.committee_id, 
	c.name AS committee
FROM members m
RIGHT OUTER JOIN committees c
ON m.name = c.name;
```

Output

```
+-----------+--------+--------------+-----------+
| member_id | member | committee_id | committee |
+-----------+--------+--------------+-----------+
|         1 | John   |            1 | John      |
|         3 | Mary   |            2 | Mary      |
|         5 | Amelia |            3 | Amelia    |
|      NULL | NULL   |            4 | Joe       |
+-----------+--------+--------------+-----------+
4 rows in set (0.00 sec)
```

## ex_5

寫出可以得到下方結果的 SQL 語句

Answer

```sql
SELECT 
	m.member_id, 
	m.name AS member, 
	c.committee_id, 
	c.name AS committee
FROM members m
RIGHT OUTER JOIN committees c
ON m.name = c.name
WHERE m.member_id IS NULL;
```

Output

```
+-----------+--------+--------------+-----------+
| member_id | member | committee_id | committee |
+-----------+--------+--------------+-----------+
|      NULL | NULL   |            4 | Joe       |
+-----------+--------+--------------+-----------+
1 row in set (0.00 sec)
```