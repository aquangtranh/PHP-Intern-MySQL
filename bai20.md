## Câu 20. Lấy blog và news có lượt view nhiều nhất
```
  (SELECT id,'blog' type, title, view, category_id, user_id FROM blog ORDER BY view DESC LIMIT 1)
  UNION ALL
  (SELECT id,'news' type, title, view, category_id, NULL user_id FROM news ORDER BY view DESC LIMIT 1);
```
  