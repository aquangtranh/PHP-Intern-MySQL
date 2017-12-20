## Câu 13. Lấy 5 blog mới nhất và số lượng comment cho từng blog
```
  SELECT blog.id, COUNT(comment.id) cmt_per_blog FROM blog 
  LEFT JOIN comment ON target_id = blog.id AND target_table = 'blog' 
  GROUP BY blog.id 
  ORDER BY blog.created_at DESC 
  LIMIT 5;
```
  