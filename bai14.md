## Câu 14. Lấy 3 User comment đầu tiên trong 5 blogs mới nhất
```
  SELECT DISTINCT blog_id, user.*, comment.created_at cmt_time FROM comment 
  RIGHT JOIN 
  (
    SELECT blog.id blog_id, GROUP_CONCAT(comment.user_id order by comment.created_at desc) top_cmt FROM blog   
    Left JOIN comment ON blog.id = target_id AND target_table = 'blog' 
    GROUP BY blog.id  
    ORDER by blog.created_at DESC 
    LIMIT 5
  ) total ON comment.target_id = total.blog_id and target_table = 'blog' 
  LEFT JOIN user ON user.id = comment.user_id AND FIND_IN_SET(user.id, top_cmt) <= 3 
  ORDER BY blog_id, cmt_time DESC;
```
  