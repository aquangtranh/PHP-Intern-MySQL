## Câu 9. Lấy số lượng comment trung bình trên mỗi blog (Update: Lấy số lượng comment trung bình của tất cả blog)
```
  SELECT AVG(cmt_per_blog) FROM   
  (
    SELECT COUNT(*) AS cmt_per_blog FROM comment 
    WHERE target_table = 'blog' 
    GROUP BY target_id
  ) AS blogcomment;
```
  