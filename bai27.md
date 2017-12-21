## Câu 27. Blog của user đang được user có id = 1 follow
```
  SELECT * FROM blog WHERE 
  user_id IN 
  (
    SELECT user.id FROM user 
    INNER JOIN follow ON user.id = to_user_id
    WHERE from_user_id = 1
  );
```
  