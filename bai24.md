## Câu 24. Lấy 1 blog và 1 news có số lượng comment nhiều nhất
```
  (
    SELECT target_id, target_table, count(comment.id) cmts FROM blog 
    INNER JOIN comment on comment.target_id = blog.id and comment.target_table = 'blog' 
    GROUP BY blog.id 
    ORDER BY cmts DESC 
    LIMIT 1
  )
  UNION ALL
  (
    SELECT target_id, target_table, count(comment.id) cmts FROM news 
    INNER JOIN comment on comment.target_id = news.id and comment.target_table = 'news' 
    GROUP BY news.id 
    ORDER BY cmts DESC 
    LIMIT 1 
  );
```
  