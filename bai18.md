## Câu 18. Lấy số lượng Blog active của user có id là 1,2,4
```
  SELECT user_id, COUNT(*) AS active_blogs FROM blog 
  WHERE is_active = 1 AND user_id IN (1,2,4) 
  GROUP BY user_id;
```
  