## Câu 19. Lấy 5 blog và 5 news của 1 category bất kỳ
```
  SET @category_id = (SELECT id FROM category ORDER BY RAND() LIMIT 1);
  
  (SELECT id,'blog' type, title, view, category_id, user_id FROM blog WHERE category_id = @category_id LIMIT 5)
  UNION ALL
  (SELECT id,'news' type, title, view, category_id, NULL user_id FROM news WHERE category_id = @category_id LIMIT 5);

```
  