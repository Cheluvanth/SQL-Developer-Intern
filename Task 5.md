### The two related tables are customers and account:





#### Using INNER JOIN:

select c.first\_name, c.last\_name, a.account\_number from customers c

inner join account a

on c.customer\_id = a.customer\_id;



#### Using left join:

select c.first\_name, c.last\_name, a.account\_number, a.balance from customers c

left join account a

on c.customer\_id = a.customer\_id;



#### Using right join:

select c.first\_name, c.last\_name, a.account\_number, a.balance from customers c

right join account a

on c.customer\_id = a.customer\_id;



#### Using full join:

select c.customer\_id, c.last\_name, a.account\_number from customers c

full join account a

on c.customer\_id = a.customer\_id;















