---
layout: post
title:      "Rails Project: Pet Job Board"
date:       2019-08-25 17:09:00 +0000
permalink:  rails_project_pet_job_board
---


For the Rails project I had chosen to create a Job Board App for animal related job openings. During the making of the project I noted the importance of several factors.

## Planning
After brainstorming an idea it is vital to properly map out the parts. What are the models? What will the user interact with? How do you imagine the user to navigate?
I find writing out the app to be most effective with a pen and paper. During this process I had also mapped out the potential associations between the models along with the information their tables would hold. Taking the time to brainstorm the project will also clarify which table should become the join table. 
While working halfway through the project I had to revist and modify my vision. Revising the project I had to stay focused on the requirements and take note of potential future features. 


## Use of MVC and CRUD
Working one method at a time, not every controller needs to have full CRUD features. Controllers are modified to work and contain only the parts necessary to function based on the desired features/ outcome. In the case of my project the join table was the jobs model. The model of the join table should contain the id of the two items it is connecting along with any attributes. The job controller needed to contain the CRUD design for the ability to add a job posting. 
Since company is associated to a job via `has_many` the job controller needed to have the ability to check if a job was already nested (to a company). While working on the project it was critical to ensure the associations were established between the models, otherwise it would result in an error message. When creating/modifying views is helpful to inspect the page to check that the form helper is propely generating the  HTML desired.
 

## Authentication
The app gives the user two choices to sign up. The gem bcrypt is used to provide password security and allows `has_secure_password ` to be used in the User model. The Sessions controller handles the cookies when the user is logged in. The gem omniauth allows for the login of a 3rd party in this case Facebook via uid (stored as a string in the user table). In the config > routes.rb file there are a group of specific routes handing the sign up, login (for returning users), sign out functions. The key and secret codes are stored in a `.env` file within the root directory. This file name is listed in the `.gitignore` file, so that it does not get pushed to github. The password of the user is not revealed.


Overall, working with Ruby on Rails was a great excerise of all the knowledge learned thus far. I was able to combine and apply the techniques from the labs to bring an idea to life. Thanks to Rails and all its magic.





