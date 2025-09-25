#### Using select \* and specific columns



##### select all columns:



select \* from customers;



##### select specific columns:



select first\_name,last\_name,phone\_number from customers;



##### select data from two tables:



select c.first\_name,a.account\_type,a.balance 

from customers c join account a

on c.customer\_id = a.customer\_id; 



##### Using where



select \* from account

where balance > 2000.00;



##### Using AND



select \* from customers

where branch\_id = 101 and first\_name = 'manu';

##### 

##### Using OR



select \* from branch 

where branch\_address = 'mandya' or branch\_address = 'muysuru';



##### Using FILTER



select \* from account

where balance between 5000.00 and 7000.00;



##### Sort with ORDER BY



##### Sort by ascending:



select first\_name,last\_name from customers

order by last\_name asc;



##### Sort by descending:



select \* from account

order by balance desc;



##### Sort by multiple columns:



select \* from transaction

order by account\_number desc,

amount asc;













&nbsp;

