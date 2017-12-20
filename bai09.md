## Câu 9. Lấy số lượng comment trung bình trên mỗi blog (Update: Lấy số lượng comment trung bình của tất cả blog)
```
  SELECT AVG(cmt_per_blog) avg FROM 
  (
    SELECT COUNT(comment.id) cmt_per_blog FROM blog 
    LEFT JOIN comment ON target_id = blog.id AND target_table = 'blog' 
    GROUP BY blog.id 
  ) blogcomment;
```
  