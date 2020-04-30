---
layout: post
title:      "Creating a CMS application using Rails"
date:       2020-04-26 13:51:14 -0400
permalink:  creating_a_cms_application_using_rails
---



**What is Rails?**

Ruby on Rails, or Rails, is a server-side web application framework written in Ruby under the MIT License. Rails is a model–view–controller framework, providing default structures for a database, a web service, and web pages. Many major companies, such as Twitter and AirBnB, use Rails. 



**Project Requirements**

For the Rails module, I decided to build a personal finance application that would allow users to create a budget, track transactions, and calculate how much they have spent from their budget. The goal of the project is to create an application that manages related data through complex forms and RESTful routes.

The application must also: 
- Include at least one has_many relationship (x has_many y; e.g. User has_many Recipes) 
- Include at least one belongs_to relationship (x belongs_to y; e.g. Post belongs_to User)
- Include at least two has_many through relationships (x has_many y through z; e.g. Recipe has_many Items through Ingredients)
- Include at least one many-to-many relationship (x has_many y through z, y has_many x through z; e.g. Recipe has_many Items through Ingredients, Item has_many Recipes through Ingredients). The "through" part of the has_many through includes at least one user submittable attribute, that is to say, some attribute other than its foreign keys that can be submitted by the app's user (attribute_name e.g. ingredients.quantity). 

In addition, the application must: 
-  allow a user the option for third party signup/login
- form display of validation errors
- include nested resources. 


**Tips on Building Your Project**
1. Build something you would want to use. Setting up your project is much simplier if you create something you could see yourself using in your everyday life. Functionality and user interface will be easier to envision when you become the user. 
2. Use validations to secure user accounts and to prevent invalid data from persisting to the database. `validates :email, uniqueness: true` included as a macro in your user file will ensure that a useremail is unique and can only sign up for an account once. 
3. Use the 'bcrypt' gem in your gemfile to have access to the has_secure_password macro. This macro stores an encrypted versions of the users password in your db to prevent manipulation of user data. 





