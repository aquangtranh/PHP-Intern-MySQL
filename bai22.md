## Câu 13. Lấy 5 blog mới nhất và số lượng comment cho từng blog
```
  SELECT target_id AS blog_id, count(*) AS amount_of_comment FROM comment AS c
  INNER JOIN blog AS b ON c.target_id = b.id 
  WHERE target_table = 'blog' 
  GROUP BY target_id 
  ORDER BY b.created_at DESC 
  LIMIT 5;
```
  