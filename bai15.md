## Câu 15. Update rank user = 2 khi tổng số lượng comment của user > 20
```
  UPDATE user SET rank = 2 
  WHERE id IN 
    (
      SELECT user_id FROM comment 
      GROUP BY user_id HAVING COUNT(*) > 20
    );
```
  