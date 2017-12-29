## Câu 4: Select 10 blog mới nhất đã active
```
  SELECT * FROM blog 
  WHERE is_active = 1 
  ORDER BY created_at DESC 
  LIMIT 10;
```
