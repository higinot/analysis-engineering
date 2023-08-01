# Aulão SQL: Atividades Práticas

Qual o nome e preço do produto mais barato da Northwind?
```
SELECT product_name  FROM products p
Order by standard_cost
LIMIT 1;
```
---

Qual o preço do produto com mais unidades em estoque?
```
SELECT product_name  FROM products p
Order by reorder_level DESC
limit 1;
```

---
Qual o 1o pedido da Northwind?  por orderDate

```
SELECT * FROM orders o
ORDER BY order_date 
LIMIT 1;
```
---
Qual o ultimo pedido da Northwind? por orderDate
```
SELECT * FROM orders o
ORDER BY order_date DESC
LIMIT 1;
```
---
Quais os 10 produtos mais baratos com estoque > 10?
```
SELECT * FROM products p 
WHERE reorder_level > 10;
```
---
Quais os pedidos do produto Ipoh Coffee
```
SELECT p.product_name, od.order_id  FROM order_details od 
LEFT JOIN products p ON p.id = od.product_id
WHERE p.product_name LIKE "%Coffee%";
```
---
Quais os pedidos dos clientes que tem endereço(customers.country) no Brazil?
```
SELECT * FROM order_details od 
LEFT join orders o ON o.id = od.order_id 
LEFT JOIN customers c ON c.id = o.customer_id 
WHERE c.country_region LIKE "%Brazil%";
```
---
Quais o total de pedidos do produto Ipoh Coffee?
```
SELECT SUM(quantity) FROM order_details od 
LEFT JOIN products p ON p.id = od.product_id
WHERE p.product_name LIKE "%Coffee%";
```
---


Quais  a quantidade de pedidos dos clientes que tem endereço no Brasil?
```
SELECT COUNT(*) FROM order_details od 
LEFT join orders o ON o.id = od.order_id 
LEFT JOIN customers c ON c.id = o.customer_id 
WHERE c.country_region LIKE "%Brazil%";
```