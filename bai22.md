## Câu 22. Lấy danh sách user đã comment trong 2 blog mới nhất
```
  SELECT * FROM user 
  WHERE id IN 
  (
    SELECT comment.user_id FROM (SELECT * FROM blog ORDER BY created_at DESC LIMIT 2) new_blogs 
    INNER JOIN comment ON comment.target_id = new_blogs.id AND target_table = 'blog' 
  )
```
  