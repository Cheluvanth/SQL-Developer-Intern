### TOOL   : SQL DEVELOPER

# DOMIN  : BANK



### Entities

#### 1\. Customers:

   \* Attributes: customer\_id(primary key),first\_name,last\_name,address,phone\_number,branch\_id.

#### 2.Account:

   \*Attributes: account\_number(primary key),account\_type,balance,open\_date.

#### 3.Transcation:

   \*Attributes: transcation\_id(primary key),transcation\_date,amount,transcation\_type.

#### 4.Branch:

    \*Attributes: branch\_id(primary key),branch\_name,branch\_address.



### Relationship

1\. **Customers and Account** : this is modeled by adding primary key of the **customers table(customer\_id) as a foreign key in account table.**

2\. **Account and Transaction** : this is modeled by adding primary key of **the account table(account\_id) as a foreign key in transaction table**.

3\. **Branch and Customers** : this is modeled by adding primary key of the **branch table(branch\_id) as a foreign key in customers table.**



### Tables

#### Branch table



create table Branch

(

branch\_id int primary key,

branch\_name varchar(20) not null,

branch\_address varchar(20)

);



#### customers table



create table customers

(

customer\_id int primary key,

first\_name varchar(20) not null,

last\_name varchar(20) not null,

address varchar(20),

phone\_number varchar(10),

branch\_id int,

foreign key(branch\_id) references branch(branch\_id)

);



#### Account table



create table account

(

account\_number int primary key,

customer\_id int,

account\_type varchar(20) not null,

balance decimal(10, 2) default 0.00,

open\_date date,

foreign key (customer\_id) references customers(customer\_id)

);



#### Transaction table



create table transaction

(

transaction\_id int primary key,

account\_number int not null,

transcation\_date timestamp not null,

trancation\_type varchar(20) not null,

amount decimal (10, 2) not null,

foreign key (account\_number) references account(account\_number)

);





#### **PRIMARY KEY:**



\- PK is used to identify a record(row) uniquely in a table

\- It will not allow duplicates and it will not allow NULL Values

\- A PRIMARY KEY is combination of UNIQUE and NOT NULL.

      PK = UNIQUE + NOT NULL

\- We can have ONLY ONE primary key in a table



#### FORIEGN KEY:



\- A FK is a referential intergrity  constraint which  creates a relationship between any two tables.

\- When we create FK, the two tables will be linked(relationship) (master \& child tables)

\- Any data we enter in child, that same should be present in Master table.. If not, child record will fail.

\- FK is also called as referential integrity between any two tables

\- FK is created in  a child table always

\- To create a FK in child we should have a common column in master table

  (A column might have different name but it should have same datatype)

\- The master table's PK = The Child Table's FK

\- FK can take DUPLICATE values.

\- FK can take NULL values. (To stop the NULL on FK, we can add NOT NULL constraint to that column)

