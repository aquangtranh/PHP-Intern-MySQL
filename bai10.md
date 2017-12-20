## Câu 10. Lấy Category có tồn tại blog hoặc news đã active (không được lặp lại category)
```
  SELECT DISTINCT category.* FROM category  
  INNER JOIN blog ON category.id = blog.category_id 
  INNER JOIN news ON category.id = news.category_id 
  WHERE blog.is_active = 1 OR news.is_active = 1;
```
  