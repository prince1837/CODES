# Migration
## Migrations & Seeding
What are migrations?
Migrations are a way to make database changes or updates, like creating or dropping tables, as well as updating a table with new columns with constraints via generated scripts. We can build these scripts via the command line using knex command line tool.




## The role of migrations
Over time, as we make changes to our application business logic, we will notice that the initial schema, that we thought was appropriate for our needs, becomes out of sync with new features introduced in the application.

While developing web app with Node JS no framework provides proper solution to migration, For this purpose Knex JS as Node JS database migration tool seems best approach so far.
Knex.js is a query builder for relational database. It supports databases like MYSQL, Postgres, MSSQL, MariaDB, SQLite3, Oracle and Amazon Redshift.
In this article will introduce some basic concept of Knex JS as Node JS Database Migration Tool.
Installation
To use Knex CLI options its recommended to install knex globally first
		
		npm install knex -g
		
For this demo purpose we will use MySQL, so we need to install Knex and Node JS MySQL driver:

		npm install knex –save
		npm install mysql –save
		
Usage of Knex JS as Migration Tool
Knex.js is using knexfile.js for database connection and migration logic.
Create this file in root of your project using following command :

		knex init
		
It will create knexfile.js with different environments (development, staging, production).
We have used two environments in knexfile.js, which looks like below:

### How you will start:
you can see that in your database two files are created automatically. And also you can see on vs code that place ‘knex/migration’ name of the folder created.
After that just create a js file so you can use this one code 

		knex migrate: make “file name”
		
After that, you can see a .js file created and if you will look in the file the you can see two files are there. 
	
		exports.up= function(knex){}
		exports.down=function(knex){}


After that just create table inside the .js file like this one.
		
		exports.up = function(knex, Promise) {
		  return knex.schema.createTable("City", function(t) {
		    t.increments("id").primary();
		    t.specificType("cityName").notNullable();
		    t.specificType("state").notNullable();
		    t.specificType("country").defaultsTo("US");
		    t.timestamp("createdAt", { useTz: true });
		    t.timestamp("updatedAt", { useTz: true });
		  });
		};
		
		exports.down = function(knex, Promise) {
		  return knex.schema.dropTableIfExists("user");
		};
after that U can use knex query to create table or update table and whatever you want to do you can write query for that.
then you will run this command:

		knex migrate:latest

If you want to delete the file then use rollback command: 

		knex migrate: rollback


Migration file generate two function up and down. Up function is used to create new table or modify existing table. Down function is use for rollback.
Structure of a migration file
There are two functions within your newly created migration file. The first is exports.up, which specifies the commands that should be run to make the database change that you'd like to make. Usually you'll be running one or more commands found in the schema builder section of the Knex documentation. These are things like creating database tables, adding or removing a column from a table, changing indexes, etc.
The second function within your migration file is exports.down. This functions goal is to do the opposite of what exports.up did. If exports.up created a table, then exports.down will drop that table. If exports.up added a column, then exports.down will remove that column. The reason to include exports.down is so that you can quickly undo a migration should you need to.
 
Seeding Your Database
Similar to migrations, the knex module allows us to create scripts to insert initial data into our tables called seed files! If we have relations on our tables, the seeding must be in a specific order to so that we can rely on data that might already be in the database. For example, we must seed the users table first because our tasks table must validate a user id foreign key that already exists.
Lets create some seed files in this order:

		$ knex seed:make 01_users
		$ knex seed:make 02_tasks
Now lets insert some data into our seed scripts:
Example 01_users.js

		exports.seed = function(knex, Promise) {
		 // Deletes ALL existing entries
		   return knex('user').insert([
		     {
		       id: 10,
		       email: 'nigel@email.com',
		       password: 'dorwssap'
		     },
		     {
		       id: 8,
		       email: 'nakaz@email.com',
		       password: 'password1'
		     },
		     {
		       id: 9,
		       email: 'jaywon@email.com',
		       password: 'password123'
		     }

		   ]);
		};
		
How to call seeds file one by one?
So if you want to call one by one seed file you can run this code:

		knex seed:run --specific=’full file name’
For specific in migrate create table:

		Knex migrate:latest --specific=’full file name’
