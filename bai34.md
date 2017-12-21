## Câu 34. Tính điểm cho user có email là minh82@example.com trong bảng comment. Cách tính điểm:
 Trong bảng comment với taget_table = "blog" tính 1 điểm, taget_table = "news" tính 2 điểm.
```
  SELECT email, SUM(total) point FROM 
  (
    SELECT email, COUNT(comment.id) * 2 total FROM comment 
    INNER JOIN user ON comment.user_id = user.id 
    WHERE target_table = 'blog' AND email = 'minh82@example.com' 
    GROUP BY email 
    UNION ALL 
    SELECT email, COUNT(comment.id) total FROM comment 
    INNER JOIN user ON comment.user_id = user.id 
    WHERE target_table = 'news' AND email = 'minh82@example.com' 
    GROUP BY email 
  ) news_blogs
  GROUP BY email 
```
  