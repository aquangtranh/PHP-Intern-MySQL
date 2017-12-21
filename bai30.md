## Câu 30. Lấy 1 comment(id_comment, comment) mới nhất và thông tin user của user đang được follow bởi user 1
```
  SELECT comment.id AS id_comment, comment, user.*, user.id AS user_id  FROM comment 
  INNER JOIN user ON comment.user_id = user.id 
  INNER JOIN follow AS f ON user.id = to_user_id 
  WHERE from_user_id = 1
  ORDER BY comment.created_at DESC 
  LIMIT 1;
```
  