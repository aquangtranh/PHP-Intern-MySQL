## Câu 10. Lấy Category có tồn tại blog hoặc news đã active (không được lặp lại category)
```
  SELECT DISTINCT c.id, c.title, description FROM category AS c 
  INNER JOIN blog AS b ON c.id = b.category_id 
  INNER JOIN news AS n ON c.id = n.category_id 
  WHERE b.is_active = 1 OR n.is_active = 1;
```
  