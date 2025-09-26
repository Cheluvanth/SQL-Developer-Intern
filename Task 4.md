## Appling aggregate functions on numeric columns

#### 

#### Using sum:



select sum(balance) as total\_bank\_balance from account;

##### 

##### Using max:



select max(balance) as highest\_balance from account;



#### Using min:



select min(balance) as lowest\_balance from account;



#### Using avg:



select avg(amount) as avg\_transaction\_amount from transaction;



#### Using count:



select count(transaction\_id) as total\_transactions from transaction;





#### Using GROUP BY to categorize





##### Total balance per customers:



select customer\_id,sum(balance) as total\_balance from account

group by customer\_id;

#### 

##### Count transaction by type:



select transaction\_type,count(\*) as count\_of\_type from transaction

group by transaction\_type;





##### Max balance per account type:



select account\_type, max(balance) as max\_balance from account

group by account\_type;





#### Filter groups using HAVING





##### Customers with total balance:





select customer\_id, sum(balance) as total\_balance from account

group by customer\_id having sum(balance) > 1000.00;





##### Account types with multiple accounts:





select account\_type, count(account\_number) as account\_count from account

group by account\_type having count(account\_number) > 1;





##### Branches with many customers:



select branch\_id, count(customer\_id) as customer\_count from customers

group by branch\_id having count(customer\_id) >= 2;













