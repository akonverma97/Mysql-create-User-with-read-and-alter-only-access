# Mysql-create-User-with-read-and-alter-only-access
# Introduction
There are times when you need to create a user only to have read and alter access to a database. The user can view,read and alter the data in the database but they cannot drop and create database structure.
# Creating a New User Account
To create a read alter only database user account for MySQL do the following steps: 
First, login as a MySQL administrator from your terminal / command prompt using the following command:

```
mysql -u root -p
```

You’ll prompted to enter the password. Type the password for the root account. 
Create a new MySQL user account.

```
CREATE USER 'mysqluser'@'%' IDENTIFIED BY 'Password';
```

The % in the command above means that the user report can be used to connect from any host. You can limit the access by defining the host from where the user can connect. Omitting this information will only allow the user to connect from the same machine.
Grant the SELECT privilege to users.

```
GRANT ALTER, CREATE ON databasename.* TO 'mysqluser'@'%';
```

Execute the following command to make the privilege changes saved and take effect.

```
FLUSH PRIVILEGES;
```

Type quit to exit from the MySQL shell.
 
```
create user 'user91'@'localhost' identified by 'google';
```

```
grant all privileges on *.* to 'user91'@'localhost';
```

```
revoke drop on *.* from 'user91'@'localhost';
```

```
flush privileges;
``` 
Example:


```sh
create user '<username>'@'%' identified by 'PASS'; 
grant all privileges on  <DBNAME>.* to '<USERNAME>'@'%';
flush privileges;
``` 
