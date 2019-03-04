---
layout: post
title:      "Be the MVP of MVC"
date:       2019-03-04 15:42:21 +0000
permalink:  be_the_mvp_of_mvc
---


Understanding MVC is important when building interactive webpages and ensuring that your web application is working the way you want it to work. Let's start with understanding routes. Routes are like the direction you want your web applciation to take. If the user wants the main page, you set your route to display the main or `index` page (is what we will typicalliy be calling it. If your user wants to submit data into a form that is on the page, your route will redirect your web application to retrieve the data, persist it, and tell it to do something else, like display to the user the information they just inputed!

Next, lets review what MVC stands for:<br>
**M**- Models <br>**V**- Views<br>**C**- Controller

We'll use the metaphor of a restaurant for understanding what these things are:

**Models**<br>
<a href="https://imgur.com/TzRJzkx"><img src="https://i.imgur.com/TzRJzkx.png" title="source: imgur.com" /></a><br>
Models are where your "back end" information is written. Usually this will be where your classes and instance methods are defined and created. This is also where your classes connect to your database (if you are using one, usually you will be) and your web application can store, call, update, and delete persisted data in the database! We compare it to the chef in a restaurant because it is the part of the web application creating the orders for the user, whether its a query for the website layout, a form, or existing data!

**Views**<br>
<a href="https://imgur.com/Kx0ou3P"><img src="https://i.imgur.com/Kx0ou3P.gif" title="source: imgur.com" /></a><br>
Views are on the other side of the spectrum- it's the user or the browser interacting with the web applciation! This is the person who is submitting queries, requrests, or viewing the web application. In our restaurant metaphor, they are the customer who ordered the food or the menu that provides options on what the customer can order (or what they can do on our web applciation). Your views is usually a folder where you will keep your documents for code that produces HTML and CSS code that will render pages and forms for the user to interact with and view.

**Controller**<br>
<a href="https://imgur.com/ZRAy2AA"><img src="https://i.imgur.com/ZRAy2AA.jpg" title="source: imgur.com" /></a><br>
On their own, our *models* and *views* wouldn't know about each other, so our chefs will be cooking without anyone to eat the food and our customers will be hungry and unable to relay their order to the chefs! The middle man is our controler, or our waiter. Our waiter receives query from the views (receives order from customer), brings the query to the model (brings order to chef), and returns to the user what their query requested (returns customer order from chef)!

