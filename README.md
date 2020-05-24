# Java-Mysql-Simple-Login-Web-application

This is a simple demonstration project to showcase conatinerization of Java web application and Mysql database in docker and Kubernetes environment.

# vkloginwebapp-sql-worked
this is worked with sql tooo

#####RDS CREATION #######

=> You need to create One RDS by choosing below SQL(5.6) version(because it is stable version)
=> Once the rds is created, then please connect it to your SQL workbench or your local sql
=> Create a database and table by using below queries
=> Make sure to open required ports in rds security group
=> Modify rds endpoint details in /src/main/webapp/userRegistration.jsp and login.jsp

SQL Queries:
DB creation:
CREATE SCHEMA demo DEFAULT CHARACTER SET 'utf8mb4' DEFAULT COLLATE 'utf8mb4_bin' ;

User creation and granting permissions to the user 
CREATE USER 'admin'@'<rds-endpoint>' IDENTIFIED BY 'password';
GRANT ALL ON demo.* TO 'admin'@'<rds-endpoint>';

Creating table:
CREATE TABLE IF NOT EXISTS demo.users (username VARCHAR(100) PRIMARY KEY,first_name VARCHAR(100),last_name VARCHAR(100),email VARCHAR(100),password VARCHAR(100),regdate DATE);

Insert the data for testing:
insert into demo.users(first_name, last_name, email, username, password, regdate) values ('veerendra','kumar','vk@gmail.com','vktholeti','password', CURDATE());

####CONNECTING SQL DATABASE from SQL in ubuntu/linux ###########33
mysql -h <rds endpoint> -u admin -P 3306 -p <database'name>  (Note: if you donthave any database give null value for -p )




