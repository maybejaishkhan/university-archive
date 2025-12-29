Database Administration Theory - Finals Notes
# 1. Database Transactions
A **Transaction** is a logical unit of work. They are a bunch of statements that are run together.

A Transaction starts with the `BEGIN TRANSACTION` statement.

A Transaction ends with either
1. The `COMMIT` command -> used to save all the changes made. 
2. The `ROLLBACK` command -> used to undo all the changes made.
## Example

Lets say we created a transaction and named it **example**.
```sql
BEGIN TRANSACTION example;
```

In this transaction, we create a table and call it **friends**.
```sql
CREATE TABLE friends (
name VARCHAR(30) NOT NULL,
residence VARCHAR(60),
age INTEGER(2)
);
```

We then insert 3 rows to this table.
```sql
INSERT INTO friends VALUES ('Yasir', 'Unit 7', 21);
INSERT INTO friends VALUES ('Subhan', 'City', 21);
INSERT INTO friends VALUES ('Arif', 'Isra', 21);
```

To save these changes we need to use `COMMIT`.
```sql
COMMIT example;
```

Now for some reason we get some kind of an error, bug or issue. We can use `ROLLBACK` to undo all the changes made.
```sql
ROLLBACK;
```

`COMMIT` creates a savepoint called the **commit point** or the **synch point**. The system maintains a **log** of all these things.

## ACID Properties
A Database Transaction must be **ACID**. It stands for:

*Atomicity* -> It means that every transaction either succeeds completely or fails completely and there is no in-between. 

*Consistency* -> It means that every transaction leaves the database in a consistent or correct state, after it is completed.

*Isolation* -> It means that every transaction must not affect others directly and their privacy is maintained. 

*Durability* -> It means that every transaction is permanent and is recorded no matter what.

## Database Recovery
We use transactions for **Database Recovery** which means in case of any issue/failure, recovering back the database itself that didn't have the issue (when it was correct/consistent).

There can two types of failures. Only **soft crashes** can be recovered using Transactions.
1. System Failure (*Soft Crash*) -> Affects the database but doesn't damage it.
2. Media Failure (*Hard Crash*) -> Damages the database.

![[Pasted image 20240320033720.png]]
In this image, we have 5 transactions.
- **Transaction 1** (T1), **Transaction 2** (T2) and **Transaction 4** (T4) all completed successfully before System Failure.
- **Transaction 3** (T3) and **Transaction 5** (T5) ended after system failure. We can recover through them using `ROLLBACK`.
---
# 2. Transaction Concurency
*It refers to the fact that DBMS typically allow many transactions to access the same database at the same time, without the data getting garbled/corrupted*.
## Concurrency Problems
There can be many different concurrency problems in a database.
### The ==Lost Update== problem 
It happens when two transactions are trying to change the same data. A change done to the data by a transaction is lost as it is overwritten by the change done by another transaction.
#### Lost Update Example
Lets say we have two Transactions.
```sql
-- Transaction 1
BEGIN TRANSACTION T1;
SELECT * FROM employees WHERE salary = 1000; --READ
UPDATE employees SET salary = salary + 100 WHERE salary = 1000; --ADD 100
COMMIT; --UPDATE

-- Transaction 2
BEGIN TRANSACTION T2;
SELECT * FROM employees WHERE salary = 1000; --READ
UPDATE employees SET salary = salary + 200 WHERE salary = 1000; --ADD 200
COMMIT; --UPDATE
```
##### What should happen
1. T1 - `READ`  (Salary = 1000)
2. T1 - `ADD 100` (1000 + 100 = 1100)
3. T1 - `UPDATE` (Salary => 1100)
4. T2 - `READ` (Salary = 1100)
5. T2 - `ADD 200` (1100 + 200 = 1300)
6. T2 - `UPDATE` (Salary => 1300)
##### What happens instead
1. T1 - `READ`  (Salary = 1000)
2. T2 - `READ` (Salary = 1000)
3. T1 - `ADD 100` (1000 + 100 = 1100)
4. T2 - `ADD 200` (1000 + 200 = 1200)
5. T1 - `UPDATE` (Salary => 1100) **UPDATE LOST**
6. T2 - `UPDATE` (Salary => 1200)

### The ==Uncommitted Dependency== problem
It happens when two transactions are run concurrently and one rollbacks before the other has accessed data.
#### Uncommitted Dependency Example
Lets say we have two Transactions.
```sql
-- Transaction 1
BEGIN TRANSACTION T1;
SELECT * FROM employees WHERE salary = 1000; --READ
UPDATE employees SET salary = salary + 100 WHERE salary = 1000; --ADD 100
COMMIT; --UPDATE
ROLLBACK; --ROLLBACK

-- Transaction 2
BEGIN TRANSACTION T2;
SELECT * FROM employees WHERE salary = 1000; --READ
UPDATE employees SET salary = salary + 200 WHERE salary = 1000; --ADD 200
COMMIT; --UPDATE
```
##### What should happen
1. T1 - `READ`  (Salary = 1000)
2. T1 - `ADD 100` (1000 + 100 = 1100)
3. T1 - `UPDATE` (Salary => 1100)
4. T1 - `ROLLBACK` *Undo all changes by T1* 
5. T2 - `READ` (Salary = 1000)
6. T2 - `ADD 200` (1000 + 200 = 1200)
7. T2 - `UPDATE` (Salary => 1200)
##### What happens instead
1. T1 - `READ`  (Salary = 1000)
2. T1 - `ADD 100` (1000 + 100 = 1100)
3. T1 - `UPDATE` (Salary => 1100)
4. T2 - `READ` (Salary = 1100) **READS UNCOMMITTED DATA**
5. T2 - `ADD 200` (1100 + 200 = 1300)
6. T1 - `ROLLBACK` *Undo all changes by T1* **LATE ROLLBACK**
7. T2 - `UPDATE` (Salary => 1300)
### The ==Inconsistent Analysis== problem
When a transaction tries to perform an aggregate function like SUM on some data and another transaction is changing the data. The aggregate function ends up reading before the change for half the time and after the change for the other half of time.
#### Inconsistet Analysis Example
Lets say we have two Transactions
and the salary column only has 2 values -> 1000, 1100.
```sql
-- Transaction 1
BEGIN TRANSACTION T2;
SELECT * FROM employees WHERE salary IN(1000, 1100); --READ
UPDATE employees SET salary = salary + 100 WHERE salary = 1000; --ADD 100
UPDATE employees SET salary = salary + 200 WHERE salary = 1100; --ADD 100
COMMIT; --UPDATE

-- Transaction 2
BEGIN TRANSACTION T1;
SELECT SUM(salary) --SUM
FROM employees --READ
```
##### What should happen
1. T1 - `READ`  (Salary1 = 1000, Salary2 = 1100)
2. T1 - `ADD 100` (1000 + 100 = 1100)
3. T1 - `ADD 200` (1100 + 200 = 1300)
4. T1 - `UPDATE` (Salary1 => 1100, Salary2 => 1300)
5. T2 - `READ SALARY1` (Salary1 = 1100)
6. T2 - `READ SALARY2` (Salary2 = 1300)
7. T2 - `SUM` (1100 + 1300 = 2400)
##### What happens instead
1. T2 - `READ SALARY1` (Salary1 = 1000) **READS BEFORE UPDATE BY T1**
2. T1 - `READ`  (Salary1 = 1000, Salary2 = 1100)
3. T1 - `ADD 100` (1000 + 100 = 1100)
4. T1 - `ADD 200` (1100 + 200 = 1300)
5. T1 - `UPDATE` (Salary1 => 1100, Salary2 => 1300)
6. T2 - `READ SALARY2` (Salary2 = 1300) **READS AFTER UPDATE BY T1**
7. T2 - `SUM` (1000 + 1300 = 2300) *Actual Sum 2400* 
**INCONSISTENT ANALYSIS**
## Transaction Concurrency Control
To avoid concurency problems is to use some kind of a concurrency control mechanism like **Locking**.
### Locking
It is a technique that can solve the previous concurrency problems. A transaction can lock a portion of the data that it is either **Reading** or **Writing** on.
#### Lock Granularity
It means how much data is locked at a time by a lock.
1. `DATABASE` Level -> Locks the entire database.
2. `TABLE` Level -> Locks a single table.
3. `PAGE` Level -> Locks a section of memory called Diskpage. *Most Used*
4. `ROW` Level -> Locks a single row of a table.
5. `FIELD` Level -> Locks a single column of a table. *Least Used*
#### Types of Locks
There are two main types of locking
1. Exclusive Lock (**X**)-> Used for Write operations like `INSERT` where no other Transaction can Read or Write the data.
2. Shared Lock (**S**)-> Used for Read operations like `SELECT` where no other Transaction can Write the data *but can Read it*.

This table shows if one Transaction can *request* for a lock if the section already has a Transaction that *holds* a lock there in the same level.

|            | Holds X | Holds S |
| ---------- | :-----: | :-----: |
| Requests X |   No    |   No    |
| Requests S |   No    |   Yes   |
#### Intent Locking Protocol
It is used to create a **Lock Heirarchy** where locks are applied on different granularity levels. The intent locks informs other transactions of its intent of placing a lock. These are used for performance increase.

1. Intent Exclusive (**IX**) -> Used to show that the Transaction wants to have an X Lock (Write) on data at a lower granularity level.
2. Intent Shared (**IS**) -> Used to show that the Transaction wants to have an S Lock (Read) on data at a lower granularity level.
3. Shared with Intent Exclusive (**SIX**) -> Mix of an IX and S lock.

This table shows if one Transaction can *request* for a lock if the section already has a Transaction that *holds* a lock there in a lower granularity level. All of these locks can be requested if there is no other lock already.

|              | Holds X | Holds SIX | Holds IX | Holds S | Holds IS |
| ------------ | :-----: | :-------: | :------: | :-----: | :------: |
| Requests X   |   No    |    No     |    No    |   No    |    No    |
| Requests SIX |   No    |    No     |    No    |   No    |   Yes    |
| Requests IX  |   No    |    No     |   Yes    |   No    |   Yes    |
| Requests S   |   No    |    No     |    No    |   Yes   |   Yes    |
| Requests IS  |   No    |    Yes    |   Yes    |   Yes   |   Yes    |
1. **X** Locks can not be requested if there is any other lock already.
2. **SIX** Locks can be requested if there is the *IS* Lock.
3. **IX** Locks can be requested if there is either the *IS* or another *IX* lock (where they can share that lock).
4. **S** Locks can be requested if there is either the *IS* or another *S* lock (where they can share that lock).
5. **IS** Locks can not be requested if there is an *X* lock.

### Deadlock
*A situation in which  two or more transactions are waiting for each other to release lock on resources so that they can proceed.*
#### Deadlock Prevention
A deadlock can be prevented if we spend resources/time to check when each transaction started and apply one of these two schemes/algorithms. The database makes sure to never let deadlocks happen.

1. **Wait - Die** Scheme -> T<sub>Old</sub> waits for T<sub>New</sub>
2. **Wound - Wait** Scheme -> T<sub>Newer</sub> waits for T<sub>Old</sub>
---
# 3. Distributed Databases
*A database system that is divided into sites that are connected together with some kind of a network. Every site acts like a fully-functional database.*

**Advantage** -> Increased Connectivity and Accessibility 
**Disadvantage** -> Increased Complexity
## Fundamental Principle
A Distributed Database System should look exactly like a Non-Distributed System. This principle can be applied using these 12 rules.
### Local Autonomy
Sites shouldn't depend on each other and should be fully autonomous.
### No Reliance on a Central Site
All sites should be treated equally and there shouldn't be a Master site.
### Continuous Operation
System should provide Reliability and Availability.
- *Reliability* -> System should stay functioning even when failures occur.
- *Availability* -> System is available at the time that is specified.
### Distributed Query Processing
Queries performed on the database should be able to interact with the entire database. *Query Optimization* becomes very important in distributed databases.
### Distributed Transaction Management
Transactions are made up of multiple *agents* which can each target a separate site. There should be recovery (done by a 2-Phase Commit) in case of failure.
### Location Independence 
*Location Transparency* -> Users don't need to know where the data is stored but it should behave like it belongs to their site)
### Fragmentation Independence
Data should be stored where it is most used so that we don't have to make a GET request everytime.
### Replication Independence
Data is replicated/copied onto multiple sites for better availability but the data must then be updated in every copy when a change is made.
### Hardware Independence 
System should work on everything regardless of Hardware (IBM, HP, DELL etc).
### Operating System Independence
System should work on everything regardless of OS (Windows, Linux etc).
### Network Independence
System should work on everything regardless of Network (Wired, Wireless etc).
### DBMS Independence
System should work on everything regardless of the DBMS used (Oracle, MySQL etc). A program called **Gateway** can be used to connect between two different DBMS. A **Middleware Data Access** can be used to make a database fully DBMS independent. 
## Problems of a Distributed Database
### Query Optimization
Also called *Query Processing*, as the Optimization done to reduce network usage needs to be distributed as well.

We create a **Summary** Table of every strategy and compare and use the one that takes the least amount of time.
### Catalog Management
Where should the System Catalog (contains Relation Variable, Views, Authorization etc.) and other required control information be stored.
#### Approaches
1. Centralized Catalog -> Stored completely in one single place.
2. Replicated Catalog -> Stored completely at every site (Replication). 
3. Partitioned Catalog -> Stored in pieces (Every site stores its own).
4. Centralized + Partitioned Catalog
#### Issues with each Approach
1. Violates `No Reliance on a Central Site` rule.
2. Violates `Local Autonomy` rule.
3. Makes Non-Local operations very expensive.
4. Better but still violates `No Reliance on a Central Site` rule.
### Object Naming
A problem can happen where the same name is given to objects by users at two different sites. We need some sort of a way to *disambiguate* the two objects. 

Giving external specific names would violate the `Location Independence` rule so we instead use the **R* approach** and to give an internal system-wide unique name. 
==CREATOR_NAME @ CREATOR_SITE_NAME.LOCAL_NAME @ BIRTH_SITE_NAME==

We can also create a Synonym for the name as it is quite long. The system creates a Synonym table at every site which store the information about the system-wide name.
```sql
CREATE SYNONYM <synonym_name> FOR <system_wide_name>;
```
### Update Propagation
Due to replication, a problem can happen where we are trying to update some object and one of the sites (which has a copy) is not available. 

We can use the **Primary Copy** scheme to deal with this by making one of the copies "The Primary Copy". Any changes that we make are done to this primary copy and then the site is responsible for *propagating* the changes to other sites.
### Concurrency Control
If there are $n$ sites then a simple implementation of concurrency control will require $5n$ messages (lock reqs + lock grants + updates + acknowledgments + unlock reqs)

We can reduce the number of messages from $5n$ to $2n+3$ by using the **Primary Copy** scheme here as well.

# 4. Database Security
**Security** refers to the protection of data against unauthorized access, alteration and destruction. while **Integrity** refers to the accuracy and validity of the data itself.

There are two main approaches of data-access control in database security.
*Discretionary Control* and *Mandatory Control*.
### Discretionary Control
Users have different access rights to different objects. This way we just tell what is allowed for each user.

```plsql
-- We can create some roles.
CREATE ROLE admin;
CREATE ROLE manager;

-- Grant authorities to those roles.
GRANT select, insert, update, delete ON employees TO admin;
GRANT select, update ON employees TO manager;

-- Then grant these roles to individual users.
GRANT admin TO Jaish, Ali;
GRANT manager TO Yasir, Subhan;
```

### Mandatory Control
Every object is labeled with a "security level" and every user has a "security clearance". An object can only be accessed by a user if the user's \[security clearance] >= object's \[security level]. This approach is used for data that needs to be kept secure and is really difficult to implement like it is used by the Military (Top Secret, Secret, Confidential).

#### Multi Level Security
This concept is the core of mandatory control and is also known as **Multi Level Security**.
Suppose you have some information and some users.
1. Information is given security levels -> Top Secret(4), Secret(3) or Confidential(2).
2. Users are given security clearances -> Top Secret(4), Secret(3) or Confidential(2).
3. We have a table - IT_Students:

| ID  | Name   | Area        | Class |
| --- | ------ | ----------- | ----- |
| 001 | Jaish  | Latifabad   | 2     |
| 002 | Arif   | Isra Colony | 3     |
| 003 | Subhan | City        | 2     |
| 004 | Yasir  | Latifabad   | 4     |
| 005 | Ali    | Kohsar      | 3     |
4. We have two users -> `U1` with clearance-2 and `U2` with clearance-3.
	1. `U1` can access data with only class-2.
	2. `U2` can access data with class-2 or 3.
	3. class-4 data can not be accessed any of them.

For any query that is run, the system adds an extra condition of `WHERE class<=user_clearance` to limit data based on the access level.

```plsql
-- If this query is run by the user U1.
SELECT * FROM IT_Students WHERE area = "Latifabad";
/* Results in the data of Jaish and Yasir. */

-- The system changes it to this query.
SELECT * FROM IT_Students WHERE area = "Latifabad" AND class <= 2;
/* Results in the data of Jaish only. */
```

## Audit Trails
They are like a detective's notebook for your computer! It keeps track of everything that happens, like a super detailed log. This way, if something goes wrong, you can figure out what happened.

It is a file that stores these things: 
- The "Request".
- The "Terminal" (from where the operation was invoked).
- The "User" (who invoked the operation).
- Date and Time of the operation
- Relation Variables(s), Tuple(s), attributes affected.
- Old values and New Values.

## Statistical Databases
They are databases that only allow queries that derive aggregated information (sums, averages, count etc.) but not queries that derive individual information. These are used for statistical analysis and simultaneously try to protect individual stored information.

Individual data CAN still be inferentially-derived from the aggregated data through some clever queries. For example here's a table Employees

| Id  | Name    | Salary | Age | Gender |
| --- | ------- | ------ | --- | ------ |
| 1   | Haris   | 50k    | 23  | M      |
| 2   | Ali     | 75k    | 25  | M      |
| 3   | Sara    | 48k    | 23  | F      |
| 4   | Hasnain | 60k    | 21  | M      |
A query like `SELECT COUNT(Salary) WHERE Age = 21  AND Gender = "F";` is allowed under the rules of "Statistical Databases" but still allows us to get the Salary of Sara. This is just one of the problem cases.

We can prevent this by adding a constraint that restricts "single row results". Even still attributes with only two possible values make it difficult to prevent this type of thing. These are called **individual trackers**.

Database Administration Labs - Finals Notes
# Oracle Database
In Oracle, there are 

- **Users** which have different rights and roles that allow them to be able to do different tasks.
- **Rights/Priveleges** are individual permissions that can be given to users.
- **Roles**, on the other hand can be given rights. These roles can then be given to different users.

The **DBA** role (Database Admin) is a special role which is given to the **System**, **Sys** and **Internal** users. This gives these users "Admin Access".

## Programs
### Opening Oracle DBMS
1. Install **Oracle Database 11g Express Edition**.
2. Go to **Start Menu**.
3. Search **SQL**
4. Run **SQL Command Line**.
5. Type `connect system/password` and press Enter.

<small>This logs you into the system user account and the password is the one that you chose when installing Oracle.</small>
### Creating a User
<small> After connecting to the system account.</small>

1. Type this code to create a user Jaish with a password 1234.
```plsql
CREATE USER jaish IDENTIFIED BY 1234
DEFAULT TABLESPACE users
TEMPORARY TABLESPACE temp
QUOTA UNLIMITED ON users;
```

We can now try login into Oracle with this account by typing `connect jaish/1234` but this is not going to work because user **Jaish** doesn't have the "privileges" to the database and can't login because of it.

### Creating a Role
<small>Now we can create a role and grant it privileges</small>.

1. Type `connect system/password` again to go to the system account.
2. Type `CREATE ROLE student;` to create a role.
3. Type this code to give privileges to the student role.
```plsql
GRANT alter session, create session, create database link, create table TO student;
```

4. Type `GRANT student TO jaish;` to give the student role to the jaish user.
5. Now we can login into the jaish user by `connect jaish/1234`.

### Deleting Users and Roles
<small>First go to the system user.</small>

To delete a user -> `DROP USER jaish CASCADE;`
To delete a role -> `DROP ROLE student;`

### Creating a Table

Type this code to create a table named **Course**.
```plsql
CREATE TABLE course(
course_id NUMBER(3),
course_name VARCHAR(50)
);
```

Our database where we are creating the table is "shared" between all the users.

# Practice Questions

1. Create 2 roles: Teachers, Students.
```plsql
CREATE ROLE Teachers;
CREATE ROLE Students;
```

2. Grant these permissions:
	1. To **Teachers** role -> Alter Session, Create Session, Create Database Link, Create Table, Create Sequence, Create Synonym, Create View
	2. To **Students** role -> Alter Session, Create Session, Create Database Link
```plsql
GRANT alter session, create session, create database link, create table, create sequence, create synonym, create view TO Teachers;

GRANT alter session, create session, create database link TO Students;
```

3. Create 7 users (password): Zia (123), Arshad (1234), Sara (12345), Fahad (1234), Nida (12345), Ali (123456), Khan (1234567).
```plsql
CREATE USER Zia IDENTIFIED BY 123;
CREATE USER Arshad IDENTIFIED BY 1234;
CREATE USER Sara IDENTIFIED BY 12345;
CREATE USER Fahad IDENTIFIED BY 1234;
CREATE USER Nida IDENTIFIED BY 12345;
CREATE USER Ali IDENTIFIED BY 123456;
CREATE USER Khan IDENTIFIED BY 1234567;
```

4. Give the Teachers role to Zia, Arshad and Sara and Give the Students role to Fahad, Nida, Ali and Khan.
```plsql
GRANT Teachers TO Zia, Arshad, Sara;
GRANT Students TO Fahad, Nida, Ali, Khan;
```

5. Login into User “Zia” Account and Create this Results table.

| result_id | course_name       | student_role_number | marks |
| --------- | ----------------- | ------------------- | ----- |
| 1         | Java              | 1                   | 50    |
| 2         | Database          | 1                   | 60    |
| 3         | CPP               | 2                   | 70    |
| 4         | Basic Electronics | 2                   | 80    |
We first have to grant a tablespace to the user.
```plsql
connect system/password

ALTER USER Zia DEFAULT TABLESPACE users QUOTA UNLIMITED ON users;
```

Now create the table.
```plsql
connect Zia/123

CREATE TABLE Results(
result_id NUMBER(10) PRIMARY KEY,
course_name VARCHAR(30) NOT NULL,
student_role_number NUMBER(10),
marks NUMBER(3)
);
```

6. Login into User “Fahad” Account and Try to view results of all students by executing query.
```plsql
connect Fahad/1234

SELECT * FROM Results;
```

<small>This won't work because Fahad doesn't have the privilege to view the table.</small>

7. Now go back to “Zia” Account and grant permissions to “Fahad and Nida” so that they view all records from results table. 
```plsql
connect Zia/1234 

GRANT SELECT ON Results TO Fahad, Nida;
```

8. Also Assign “select, insert, update and delete” permissions on “Results table” to teachers “Arshad and Sara”
```plsql
GRANT SELECT, INSERT, UPDATE, DELETE ON Results TO Arshad, Sara;
```

9. Now Login into “Sara” account and try to insert a row in Results table. 
```plsql
connect Sara/12345

INSERT INTO Results(result_id, course_name, student_role_number, marks) 
VALUES (5, English, 3, 60);
```

9. Now Login into “Arshad” account and try to delete a record having result_id of “3” Results table. 
```plsql
connect Arshad/1234

DELETE FROM Results WHERE result_id = 3; 
```

10. Delete user account of “Khan” also revoke all his permissions. 
```plsql
REVOKE ALL PRIVILEGES FROM Khan;

DROP USER Khan CASCADE;
```
