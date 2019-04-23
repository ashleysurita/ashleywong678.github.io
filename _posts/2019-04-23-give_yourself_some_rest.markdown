---
layout: post
title:      "Give yourself some REST"
date:       2019-04-23 17:17:42 +0000
permalink:  give_yourself_some_rest
---


RESTful routing has changed the way users interact without sites as well as improved how we as program create, name, organize, and understand our route patterns. Previously, when naming our url routes, random letters and numbers were used which was gibberish to the user and to us programers. Now, if we follow RESTful routes, we name them based on what they do and where they direct to, which makes more sense to everyone (it also makes it easier when we inherit code from someone else when trying to make sense of it all).

REST stands for **REpresentational State Transfer**, which is an idea that naming conventions should *represent* what they are/do. Let's map out routes for a *pets* page:

| HTTP Verb | Action | Url |
| -------- | -------- | -------|
| GET | index | /pets |
| GET | new | /pets/new |
| POST | create | /pets |
| GET | show | /pets/:id |
| GET | edit | /pets/:id/edit |
| PATCH | update | /pets/:id |
| PUT | update | /pets/:id |
| DELETE | delete | /pets/:id/delete |
We have 8 routes that we will use for a typical site applciation.
The difference between *PATCH* and *PUT* is how much we are editing. If we are editing something small, like 1 or 2 attributes, we use the *PATCH* method, this is what we will typically use as it makes our appilcation work a little faster. We use *PUT* when we are doing large edits to an object, like if we were updating all of the attributes, this we won't use often.

Lets break down all of these parts:

**HTTP Verb**- This tells our application what kind of *request* the user is making. If we are making a *GET* request, the user is asking our application *"Please show me the view for this page"*/ If they are making a *POST* request, the user is asking our application *"Create this object"* (if it's valid) and etc.

**Action**- Our action tells our application where to go. In our controllers, we have methods(actions) that know what to do with data (or stuff) from our models, performs actions and *stuff* on it, and gives it back to our user all pretty and neatly. It's basically the instructions behind the view pages.

**URL**- Our url is how we name our route. Remember when we were talking about RESTful routes? We were talking about how we are naming our website urls. This is the path that our user will take to get to a particular part of our site and what will be printed when redirected to other sites.

Become comfortable with RESTful conventions, it will come up a lot and often!
