The first thing which is you have to install Postgresql Database


For installing Postgresql 

sudo apt-get update
sudo apt install postgresql postgresql-contrib 

For opening 

		sudo -u postgres psql 

After opening your Postgresql database will look like this:>

After opening your Postgresql database will look like this:>


After that, if you want to control your database and database_users:>
For that, these are the basic Command:>
		
		\du			:for seeing your database users;
		\l			:for seeing your list of databases.
		\c databse_name 	:for use a particular database
		\d table_name 	:for seeing schema of table
		\dt 			:for use to seeing your table in a particular database
		\q			:for quit from database




Then if you want to create a database in Postgresql
Then there are basic commands which can you use:>

For creating a new user which you have to use this command:

		CREATE USER user_name WITH PASSWORD ‘password’;

For creating a new Database which you have to use this command:

		CREATE DATABASE DB_NAME;    

For change username_password which you have to  use this command:
		
		ALTER USER user_name WITH PASSWORD ‘password’;

For change owner of Database:
		
		ALTER DATABASE database_name OWNER TO user_name;



You can also watch this video which will help you to better understand.


IMPORT DATABASE IN POSTGRESQL FROM MYSQL DATABASE USING BY PGLOADER.

Installation of pgloader:

First, you have to clone a repo from Github:
You can also use this command on the terminal to make a clone:

		git clone https://github.com/dimitri/pgloader

After cloning you have to run this command to open your local pgloader Directory:

cd pgloader/
 
Then after you have to make pgloader for that you have to run this command:

		make pgloader

Maybe it will take a couple of minutes. You have to wait for it. Maybe it is stuck while making then close your terminal and run that command again.

After that, if you want to check the version of pg loader then you can run this command:

		./build/bin/pgloader --version

Then output will be like this:
	
		pgloader version "3.6.d5314a6"
compiled with SBCL 1.4.5.debian


IMPORTANT THING WHICH YOU HAVE TO REMEMBER THAT.

1, which you are going to import into the Postgresql database from MySQL which must be in MySQL and Postgresql database.
2, You must remember your username and password of the Mysql database.

3, You must remember the password and the username of your PostgreSQL of that database which you are going to use.

4, Also remember that the owner of the database you are going to use must be the user whose password you know.

5, Important things when you will run a command for import database in Postgresql from MySQL that time your code will run in pgloader only. So, before running this command you have to run “cd pgloader” if you are not in a local pgloader directory;





If these things you are following then after that you can run this command: 


		./build/bin/pgloader mysql://mysql_user_name:mysql_password@localhost/mysql_database_name postgres://posgresql_user_name:posgresql_password@localhost/posgresql_database_name

If you want to make you column in snake_case then you can run this command.

		./build/bin/pgloader --verbose --with "snake_case identifiers" mysql://mysql_user_name:mysql_password@localhost/mysql_database_name postgres://posgresql_user_name:posgresql_password@localhost/posgresql_database_name

This is a command which you will run but be aware of your user name, password and database name.

IF YOU FOLLOWED THIS ALL THINGS THEN YOU WILL BE ABLE TO SEE ALL THOSE TABLES OR THAT ONE DATABASE  WHICH YOU MADE IN MYSQL DATABASE.

# EXPORT & IMPORT Database

If you want to import datbase in your postgres Database from your local `.psql`

	psql -U username dbname < dbexport.pgsql

If you want to export databse from your postgres database in your local `.psql` file

	pg_dump -U USERNAME DBNAME > dbexport.pgsql
