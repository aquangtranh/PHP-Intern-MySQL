## Câu 25. Lấy 5 blog và 5 news mới nhất đã active
```
  (SELECT id,'blog' type, title, view, category_id FROM blog WHERE is_active = 1 ORDER BY created_at DESC LIMIT 5)
  UNION ALL
  (SELECT id,'news' type, title, view, category_id FROM news WHERE is_active = 1 ORDER BY created_at DESC LIMIT 5);
```
  