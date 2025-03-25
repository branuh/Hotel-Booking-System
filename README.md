# Hotel-Booking-System
Final Project With Emobilis

DJANGO
THis is a python web framework (a software framework that simplifies the development of web apps by providing a structure and common components (tools and libs to handle common web dev tasks) )
routing : mapping url routes to various pages or functionalities
Authentication : authorization , identity
Database integration and interaction
Session Management
Form Handling
Examples Backend Frameworks

NodeJS
Python (Flask and Django)
PHP (Laravel)
Ruby on Rails
GO (GIN, ECHO)
Frontend Framework

React JS
Next JS
Angular
Vue
A DJANGO WEBSITE
This typically consists of a single Project , that is then spilt into separates apps Instagram (case study)

user management : Logging in and out , registering , forgot password
media features : upload, edit and display media
messaging : send messages
django apps are structured to separate the logic pieces

django supports the architecural pattern of MVC.

Models : define the data. This is usually the database description and often the base layer to an app.
Views : display some or all data and also enable client interaction. HTML AND CSS things
Controllers : handles how the database and the views interact
django recognizes above as an MVT pattern

Models : define the data. This is usually the database description and often the base layer to an app.
Views : url mapping logic
Templates : HTML and CSS , where to also interact with jinja templating.
Conclusion:
A django site starts off as a project , and its built up with a number of apps that handle separate functionalities. Each app follows the MVT pattern.

Tools to work with django
Python - python --version python3 --version

pip - pip install django

python -m django --version

How to create to django projects
python -m django-admin startproject PROJECTNAME

How to run the django server
cd projectname
python manage.py runserver
How to add an app
python manage.py startapp todo
next register the app to the project , in settings.py on project folder add it to the installed apps list
How to map models to database tables (applying migrations)
Define the model
make the migrations ( python manage.py makemigrations )
apply the migrations ( python manage.py migrate )
AGENDA
Databases
Objects Relationships
Install an sqlite viewer
go to file -> settings -> plugins on sidebar
ctrl + alt + s to open settings
go to installed tab
ensure the plugin Database Tools and SQL is checked
if not present search in marketplace
double click on desired view for db
right click to check if database drivers are enabled
If not installed , click to install
right click to get to properties
check the general tab , to ensure sqlite URL is correctly mapped to your project
check the schema tab and allow the schema you want or all to visualize all schemas
Locate the schema , then double click to visualize table for app.
https://www.jetbrains.com/help/pycharm/sqlite.html#connect-to-sqlite-database
Databases
A database is an organized system for storing , managing and retrieving data in an efficient and organized manner

Maintain persitency on data. Manipulate the data
Database Structure
Key elements of the structure

Tables : primary structure for organizing data , where data is stored in rows and columns
Columns : Represents specific attributes or props for the items in each row. Each column will have a data type like text, integer or date ....
Primary Key : A unique id for each row , ensuring no row has the same Primary key , making it easier to access and manage individual records
Foreign Key : A field in one table that links to the primary key of another table , creating relationships between the tables
Database Types
Classified by how they store data, the type of relationships they support and the design

a. Relational Databases (RDBMS) use tables to store data with predefined relationships between the tables. Each table has rows and columns where relationships are established using PK and FK

examples : MySQL , PostgreSQL , Oracle , SQL server , sqlite

Advantage: High data integrity , SQL support , support for complex queries through SQL joins

b. NoSQL Databases store data in non-tabular forms , which makes them suitable for unstructured , unrelated or semi structured data Document-Oriented sequence : JSON-like documents

Example : Google Firebase , MongoDB

c. In-Memory db's : storage happens in main memory rather than disks (RAM) Example : Redis

d. Object-Oriented Databases storage of data in objects example : ObjectDB

e. Distributed databases Data is stored across different locations and interconnected through a network Example : Google Spanner , Apache Cassandra

Database Attributes and Fields (Columns)
Data types : define the kind of data to be stored in each column. (text, integer, date , boolean)
Constraint : Rules to be applied to the data to ensure data integrity (NOT NULL, NULL , UNIQUE, length)4
Indexes : Special data structures that improve query performance by allowing fast retrieval of rows usings keys columns
Schemas : Describe the structure of the db. includes the tables , relationships, views and permission.
Database Operations
CRUD operations : Create , read, update, delete
Query : retrieve specific data using SQL : Structured query language
Transactions: group operations within single units
Database Relationships
Defining how data in different tables relate to one another

One to One : Each row in one table is linked to one row in another table
One to Many : A row in one table can be linked to multiple rows in another table
Many to Many : Rows in one table are linked multiple rows in another table , often managed using a join table
ORM : Object Relational Mapping
this is a programming technique allowing us to interact with a relational db using oop. Key usage

replaces the need for writing raw SQL queries instead we use the objects to perform db operations , makes our code cleaner and more maintainable
Python Flask = SQLAlchemy ORM Python Django = Django ORM

Django ORM
Allows interaction with databases using python classes and methods rather than raw SQL. Breakdown :

Each model class represents a table in the database
Each instance/object of that class will represent a row in the table
Basic concepts of Django ORM
Model : a python class to represent the table
Querysets : A collection of db rows represented as objects which can be filtered ordered and manipulated
Migrations : A way to apply db schema changes i.e. creating tables
APIS(Application Programming Interfaces)
-Set of rules and tools that allow software applications to communicate with each other e.g. A django app can communicate with an Android app.

Defines how different software components should interact, enabling seamless data sharing and functionalities btw the application
what is REST ? (Representational State Transfer)
this is an architectural style for designing APIs
REST relies on standard HTTP methods and focuses on making systems stateless and scalable
Key features of REST
Stateless : Each request from a client contains all the info. needed to process it and the server does not store any CLIENT state
HTTP methods : Common methods
GET : Retrieve Data
POST : Create the new data
PUT/PATCH : Update data
Delete : Delete Data
Resources : Everything is treated as a resource (e.g. users , products ) and each has a unique URL
Format : Typically uses JSON or XML for data exchange
JSON (Javascript Object Notation)
JSON is a lightweight data-interchange format. Widely used in API for data exchange

JSON OBJECT -> { "key" : "value" }

JSON ARRAY [ { "key" : "value" }, { "key" : "value" }, { "key" : "value" } ]

Approach to Developing APIS
Understand Requirements
identify what the API needs to do.
Designing the API
REST way , GraphQL
design the route and specify input/output
API versioning and documentation (SWAGGER ? POSTMAN)
Build the API
select the framework to use (DJANGO , EXPRESS IN JS ,FLASK )
Implement the endpoints '/tasks' '/task/int:id' usingt the HTTP methods
validations and if necessary implement authentication.
Test the API
test the api for performance , security, and proper data handling tools (POSTMAN)
Deploy and maintain for live use.
DJANGO APPROACH TO BUILDING THE APIS
Django REST Framework
DRF is a powerful and flexible toolkit for building web apps in DJANGO Steps
Install DRF : pip install djangorestframework
Define models for data
Create serializers to convert btw JSON and model instances
Define API Views and use DRF generic views for common patterns
use routers to handle URL Routing
Using core DJANGO
popular for simpler project
DJANGO built in JSONRESPONSE and your simple views for routing functionality
Steps for creation
Create and register the second app to our project python manage.py startapp todo_api
Install DRF (djangorestframework) pip install djangorestframework
Models :
user : one to many relationship todos
tag : many to many relationship with todos
tasks : data to define todos.
task : buy groceries tag : urgent, personal

A task can have multiple tags
A tag can be associated to multiple tasks
tag : urgent Buy Groceries , Pay bills

Make the migrations python manage.py makemigrations python manage.py migrate

Set up of serializers a. create a serializers.py file

Create the viewsets in view.py :: CRUD operations

Create the urls.py file for our app

Create the urls paths for the app

Register the apps urls to the project urls

Test : using a tool like POSTMAN then run the project and test the endpoints.

open settings, get to the marketplace , search and install postman~~~~
Serializers
-Serializers are used to convert model instances to simple python data types e.g. list , dictionary , which enables them to be easily rendered into JSON

Conversely, serializers also handle converting incoming data back into django model instances for saving into database Summary a. Serialization : Converting python object i.e. model instance into JSON for API responses b. deserialization : converting incoming python objects into model instances for creating or updating records
Types of serializers in DRF (DJANGO REST FRAMEWORK)
ModelSerializer
Class that acts a shortcut i.e. it auto. generates and validates fields based on the model
Standard Serializer
Used when we need more control over the serialization process
Does not depend on the model for validation and generation , i.e. needs explicit definations.
DJANGO AUTHENTICATION
Django comes with a ready user authentication system

Handle user accounts
Permissions for users
Cookie-based user sessions
Authentication and Authorization The auth system consist of the following

User model
Permission flags : yes/no : user may perform a certain task
A configurable password hashing system
Form and view tools for logging in users and restricting content
A pluggable backend system (customize what django does by default.)
installation
happens on creation of the django project

django-admin startproject
"django.contrib.auth", : core of the authentication framework , default models (User)
"django.contrib.contenttypes", : linking to our own customization.
once you have extended the default auth model then :
make the migrations ( python manage.py makemigrations )
apply the migrations ( python manage.py migrate )
preventive measures
Define the custom user model early : let it be the first app we create
Run the migrations for above model first
Test migrations for this as we bring in our other applications
django.db.migrations.exceptions.InconsistentMigrationHistory: Migration admin.0001_initial is applied before its dependency accounts.0001_initial on database 'default'.

Assessment

Create a new django project
Create the accounts app first : so that we avoid inconsitiencies btw the authentication layer django and our new customization.
Run the migrations and test app
Bring in the other apps.
