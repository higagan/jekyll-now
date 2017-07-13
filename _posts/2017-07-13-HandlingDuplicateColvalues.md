---
layout: post
title:  Handling duplicate column values in SQL
published: true
category: SQL
---

Sometimes, we get many duplicate values in a column which was not supposed to happen. 
To check which all values are duplicate:
```sql
SELECT projectName,count(*) as count1 
FROM project
GROUP BY projectName
HAVING (COUNT(projectName) > 1 )
```
Now, one approach to remove duplicacy is to append it with some values
To do this there are two ways
1. 
```sql
UPDATE project SET projectName=projectName+CAST(idproject AS VARCHAR)
WHERE idproject NOT IN (
  SELECT MIN(idproject) 
  FROM project
  GROUP BY projectName
);
```
2. 
```sql
;WITH cte AS
(
  SELECT
		idproject,ROW_NUMBER() OVER(PARTITION BY projectName  ORDER BY projectName ) AS projectCount,
      projectName 
  FROM project
)

UPDATE cte SET projectName =projectName +'_'+CAST(idproject AS VARCHAR)
WHERE projectCount > 1
```
Now , to make sure in future its not repeated add unique constraint to this column

```sql
ALTER TABLE project
ADD UNIQUE (projectName);
```

