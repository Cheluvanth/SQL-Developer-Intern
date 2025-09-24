### Inserting data

#### 

#### Branch table



insert into branch values (101, 'canara bank', 'maddur');

insert into branch values (102, 'hdfc bank', 'mandya');

#### 

#### Customers table



insert into customers values (1, 'manu', 'm', 'tumkur', '555-1234', 101);

insert into customers values (2, 'yashu', 'c', 'maddur', '555-5678', 102);

insert into customers values (3, 'danu', 's', 'chanpatna', '555-9012', 101);

#### 

#### Account table



insert into account values (1001, 1, 'checking', 1500.50, '2023-01-15');

insert into account values (1002, 2, 'savings', 5000.00, '2024-02-20');

insert into account values (1003, 1, 'savings', 750.20, '2025-03-10');



#### Transaction table



insert into transaction values (1, 1001, '2024-04-01 10:00:00', 'deposit', 250.00);

insert into transaction values (2, 1002, '2024-12-05 11:11:00', withdrawal', 100.00);

insert into transaction values (3, 1001, '2025-07-05 15:45:00', 'withdrawal', 50.00);





### Handling missing values using null or default

#### 

#### Using null



insert into customers values (4, 'don', 'v', 'mysuru', null, 102);



#### Using default



insert into account values (1004, 2, 'savings', '2025-09-23');



#### Using update



update account

set balance = 7000.00

where account\_number = 1003;



#### Using delete



delete from customers

where customers\_id = 3;





















