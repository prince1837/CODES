how can we get data and give data from another database in mysql;
if you want to import data from another sql file so
like first you have to open the mysql database
then create database in mysql 
then making a source like this 
source, then you have to give the database of link like this `/home/shivansh/Documents/Database/turing-backend/database/tshirtshop.sql`
run this command on terminal;

    mysql -u  root -p ("database name in which you want to write a data") < ("database name from which database you want to write same thing in database "
    
And we have one thing more
if you want to dump data from your databse in sql file then run this command

      mysqldump -u  root -p ("database name in which you want to write a data") > ("database name from which database you want to write same thing in database "
    

Installing mysql-server
    
    sudo apt install mysql-server -y    

For set password in mysql for security then run this command

    sudo mysql -u root -p
    ALTER USER 'username'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
    FLUSH PLIVILEGES;
