## Câu 17. Select 10 blog mới nhất được tạo bởi các user active
```
  SELECT * FROM blog 
  INNER JOIN user ON blog.user_id = user.id 
  WHERE user.is_active = 1 
  ORDER BY blog.created_at DESC
  LIMIT 10;
```
  