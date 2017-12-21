## Câu 32. Tìm có tên(user.full_name) "Khiêu" và các thông tin trên blog của user này như: (blog.title, blog.view), title category(category) của blog này.
```
  SELECT u.id, u.full_name, b.title, b.view, c.id AS category_title FROM user AS u 
  INNER JOIN blog AS b ON b.user_id = u.id 
  INNER JOIN category AS c ON c.id = b.category_id 
  WHERE full_name LIKE CONCAT('%', CONVERT('Khiêu', BINARY));
```
  