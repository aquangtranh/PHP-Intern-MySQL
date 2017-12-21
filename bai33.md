## Câu 33. Liệt kê email user các user có tên(user.full_name) có chứa ký tự "Khi" theo danh sách như output bên dưới.
```
  SELECT GROUP_CONCAT(email SEPARATOR '; ') AS email_users FROM user
  WHERE full_name LIKE '%Khi%';
```
  