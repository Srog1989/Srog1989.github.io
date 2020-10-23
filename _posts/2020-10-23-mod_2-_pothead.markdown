---
layout: post
title:      "Mod 2- PotHead"
date:       2020-10-23 16:44:27 +0000
permalink:  mod_2-_pothead
---


Wrapping up Mod 2 and I've successfully built a functioning Sinatra application called PotHead. It's an app that is able to keep track of the plants a user has and know its water and light needs. This is pretty exciting, as it's the first time i've written code for an application that you actually get to look at in a browser! WHOA!!  In my application a user is able to use full CRUD(create, read, update, delete) on an object, in this case a plant. A user is able to sign up, log in, log out, and edit or delete their account. I generated this project with the help of the Corneal gem which you can find here (https://github.com/thebrianemory/corneal) This was very helpful in helping me set up my project files and folders, it even has the option of scaffolding which helps you get your routes set up for the application, awesome!

Once I got my routes built out it was time to decide what I wanted my user to be able to do. Thats when I created a users and an object table(plants) with the attributes I wanted each to have. Once I had my tables built I migrated the files and my schema was created. Time to write some code. Using the MVC(Models, Views, Controllers) structure I had two models. A users model which has_many plants and has_secure_password(which is able to encrypt passwords using the bcrypt gem and having a password_digest in your users table). It also validates :username, uniqueness: true to avoid duplicate usernames from being created. I also had a plants model which belongs_to_a_user and validates the attributes of the object to be true to avoid any bad data being entered into the database of my application. 


We covered a lot in our coursework in this module, and I've learned ALOT!  I learned what user authentcation was, what parameters were, associations, what a sessions hash is, how to write forms, how to style a page using css, etc. Doing the project really brought the concepts home for me. I'm very excited to be completing this project and as always, am looking forward to what Mod 3 brings me! Cheers!
