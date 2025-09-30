#### Using scalar Subquery:

##### Compare to Average:



select account\_number, balance from account 

where balance > (select avg(balance) from account);



##### Display Total Count:



select first\_name, last\_name, (select count(\*) from account) as total\_accounts\_in\_bank 

from customers where customer\_id = 1;



#### Using correlated Subquery:

##### Customers with High Balance Accounts:



select first\_name, last\_name from customers c 

where c.customer\_id in 

(select a.customer\_id from account a 

where a.balance > 1000.00 and a.customer\_id = c.customer\_id );



#### Using IN:

##### Customers with Checking Accounts:



select first\_name, last\_name from customers 

where customer\_id in 

(select customer\_id from account 

where account\_type = 'checking');



#### Using exists:

##### Customers with Transactions:



select first\_name, last\_name from customers c

where exists 

(select 1 from account a join transaction t on a.account\_number = t.account\_number 

where a.customer\_id = c.customer\_id);



