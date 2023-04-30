## Задание 1
SELECT  SUM(tt.DATA_LENGTH) , SUM(tt.INDEX_LENGTH), CONCAT(  ROUND ((SUM(tt.INDEX_LENGTH) / SUM(tt.DATA_LENGTH)) *100), ' %')  AS Отношение  
FROM INFORMATION_SCHEMA.TABLES tt  
WHERE  tt.TABLE_SCHEMA = 'sakila' ;  

## Задание 2
Убрать distinct, over (partition by c.customer_id, f.title), film f  

select concat(c.last_name, ' ', c.first_name), sum(p.amount)  
from payment p, rental r, customer c, inventory i  
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id  
GROUP BY concat(c.last_name, ' ', c.first_name)  
