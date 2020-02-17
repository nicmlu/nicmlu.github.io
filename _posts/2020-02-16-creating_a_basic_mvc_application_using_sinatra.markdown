---
layout: post
title:      "Creating a Basic MVC Application using Sinatra "
date:       2020-02-17 03:10:14 +0000
permalink:  creating_a_basic_mvc_application_using_sinatra
---


**What is Sinatra?**

Sinatra is a Domain Specific Language implemented in Ruby that's used for writing web applications. Sinatra is Rack-based, meaning it can fit into any Rack-based application stack. To simplify, Sinatra is nothing more than a set of pre-written methods that we can include in our applications to turn them into Ruby applications. Many major companies, such as Apple and LinkedIn, use Sinatra. 



**Project Requirements**

The goal of the Module 2 final project is to design a basic MVC application, which acts as a simple Content Management System (CMS). Besides utilizing Sinatra, this application should also utilize ActiveRecord to perform basic CRUD actions and SQLite3 to store and retrieve user data. 

The application must also: 

•have 2+ models.
•have user accounts with unique login attribute
•have CRUD routes
•Ensure that users can't modify content created by other users
•Include user input validations


**Project Set-Up**

To give yourself a jump start on building (probably) your first user facing application, use the corneal gem to have the file structure for a Sinatra MVC application set up for you. Find more information about the corneal gem at [here.](http://https://thebrianemory.github.io/corneal/) 

While its nice to have it all magically done for you, its important that you know the purpose of each file and what is included. It will help with future bug fixes and can serve as a model when setting up your own application without dependencies. 




**Setting up MVCs**

MVC stands for Models, Views, and Controllers. 

* Models are your object classes and inherit from ActiveRecord::Base. You can set obect associations and validations within your model class files. 
* Views are your .erb files, which include code on how the data is represented to the user. Will your application have a login page? Will you have an index page that shows all created objects? A new view should be created for every page your user may interact with. 
* Controllers are .rb files which contain your page routes, including CRUD routes, which direct your application to the appropriate path based on an http request from the browser or user input. 

When working, I tend to plan out my views first. When I know what I expect the user to see, I can then set up the models and the controller actions directing to the appropriate view. But for much of your building, you will be going back and forth between files to continue to improve functionality and clean up code. 

**Last Tips**
1. Build something you would want to use. Setting up your project is much simplier if you create something you could see yourself using in your everyday life. Functionality and user interface will be easier to envision when you put become the user. 
2. Use validations to secure user accounts and to prevent invalid data from persisting to the database. `validates :email, uniqueness: true` included as a macro in your user file will ensure that a useremail is unique and can only sign up for an account once. 
3. Use the 'bcrypt' gem in your gemfile to have access to the has_secure_password macro. This macro stores an encrypted versions of the users password in your db to prevent manipulation of user data. 





