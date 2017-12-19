## Câu 11. Lấy tổng lượt view của từng category thông qua blog và news
```
  SELECT category_id, SUM(view) AS total_views FROM 
  ( 
    SELECT category_id, view FROM blog 
    UNION ALL 
    SELECT category_id, view FROM news
  ) AS total
  GROUP BY category_id;
```
  