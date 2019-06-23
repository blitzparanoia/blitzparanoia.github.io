---
layout: post
title:      "Sinatra Project: Wanderlust"
date:       2019-06-23 19:02:56 +0000
permalink:  sinatra_project_wanderlust
---

The purpose of the Wanderlust sinatra app is to track/log places the user has traveled. Below is my experience and notes collected while creating the app.

## MVC

**Model**- logic of the application

**View**- The front end, html user interface part. composed of HTML, CSS, Javascript

**Controllers**- relays the data from browser to application and from application to browser

A database is added to the Sinatra application in order to store information. The Activerecord gem (allows for database mapping and association) is added along with the sinatra-activerecord (to access rake tasks), and rake gem (ability to create files/folders and to automate tasks).

There are also gems needed for development which include sqlite3 and tux. The shotgun gem is used to automatically reload the ‘rackup’ command, making it easier to view changes when developing Rack applications.

Creating a Sinatra application with the [Corneal gem](https://github.com/thebrianemory/corneal )  is an absolute breeze. It automatically generates a boilerplate for the application.

A db migrate folder was added with the user and the destination data table information. The user and destination model files uses Activerecord::Base and follows a has_many and belongs_to. The users has_many destinations, whiles destinations have belongs_to in the model folder. The controllers must be added to the config.ru file via ‘use’ along with `use Rack::MethodOverride`.


## RESTful route
provides mapping between HTML verbs (get, post, put, delete, update, patch)

The routes used in this project within the controllers include Get (to display and create new actions), Post (to create an action), Patch (to modify an existing action using the ID in the url) and Delete (to delete action). The controllers inherit from the Application Controller.

*NOTE: Patch, Put and Delete requests are used with Rack::MethodOverride. This is a part of Sinatra middleware the app must be told to use middleware by adding “use Rack::MethodOverride” in the config.ru


## CRUD actions - Create, Read, Update, Delete
This is a cycle of principles for databases…
CREATE : new records are generated
READ/RETRIEVE : reads data / grabs data
UPDATE : modifies records without overwriting
DELETE : deletes records

[bcrypt gem]( https://github.com/codahale/bcrypt-ruby) allows for the password to be stored securely (not in plain text). When using bcrypt the password field in the database is identified as ‘password_digest’. The model that would be associated with the password column should have ActiveRecord’s ‘has_secure_password’ line. In the controller, the password is validated to match by using ‘authenticate’.

## Overall
The experirence of using Sinatra to build an app was challenging. Using Activerecord had created a level of abstraction which required the past knowledge of knowing the 'base' was created. As the app grew it became a maze but creating a flowchart of the outline and which pages to direct to was of great assistance. Using Corneal to create the boiler plate for the app had removed the guesswork from figuring out the file structure. This had made more time to focus on developing the app itself. A challenge was minipulating the erb files and properly embedding Ruby (via substitution tags <% %>) into the HTML. It was exciting to troubleshoot and beable to redirect to the correct pages and finally properly display information as desired in the view files.
