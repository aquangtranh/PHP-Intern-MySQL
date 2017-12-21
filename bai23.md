## Câu 23. Lấy 2 blog, 2 news mà user có id = 1 đã comment
```
  (
    SELECT DISTINCT * FROM comment  
    WHERE user_id = 1 AND target_table = 'blog'
    LIMIT 2
  )
  UNION ALL
  (
    SELECT DISTINCT * FROM comment 
    WHERE user_id = 1 AND target_table = 'news' 
    LIMIT 2
  );
```
  