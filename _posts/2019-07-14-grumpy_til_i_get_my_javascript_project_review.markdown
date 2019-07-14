---
layout: post
title:      "Grumpy 'til I get my Javascript (Project Review)"
date:       2019-07-14 13:47:59 +0000
permalink:  grumpy_til_i_get_my_javascript_project_review
---


I don't think anyone says this, but the power of javascript is pretty great if you can figure out how to use it and remember all those querks.

![](https://imgur.com/a/2LHwr29)

The goal of this project was to take our existing rails project and render the same info with javascript instead of reroutinng with rails. Probably without Cernan's walkthrough videos, this would have been impossible since the syntax in this language is pretty different then what we are accustomed to. Here's a few things I've learned along the way:

Lesson 1 while doing this project- **DELETE ANY AND ALL TURBOLIKS AND COFFEE FILES**
1. First, remove the turbolinks gem from your Gemfile, delete your Gemfile.lock, and rerun your bundle.
2. go to `app/assets/javascript/application.js` and remove `//= require turbolinks`
3. in the same folder, delete all the coffee files, you can rename the file to `.js` as Cernan does in his project walkthrough
4. go to `app/views/layouts/application.html.erb` and remove anything that says `turbo links` or `remote: true`, this will mess up the connection between your javascript and view files

Lesson 2- The app will flow better if in your controller you give it the option to render html or json
This is probably a personal/style choice to me but it makes the most sense in my opinion. If something goes wrong with your javascript rendering, the default of the app will be to reroute the page using regular rails. That way your user doesn't get this weird return of JSON data and is wondering what the heck just happened and your user's experience will be uninterrupted

Lesson 3- Just use append, forget about appendChild
I spent a long time trying to figure out how to create a <ul> element so I could append <li> elements of my has_many to it when i was creating the html elements. The easiest (probably not most efficient way) I found was before iteration, throw all the elements you want to add onto your page first and append your <li>'s later. I admit it's really ugly. For example:
```
$('.main').append('<h1 class="center">Customer Accounts</h1><br><ul id="info"></ul><br><br><a href="/customers/new" class="btn">Create a Customer</a>')
```
It's so ugly...but it comes out looking like this:
```
<h1 class="center">Customer Accounts</h1>
<br>
<ul id="info"></ul>
<br><br>
<a href="/customers/new" class="btn">Create a Customer</a>
```
When your string is passed in and the page is rendered, the program is smart enough to reformat everything to look like regular html. so when you want to append the <li>, you just need to call `#info`

Lesson 4: using the url to find nested associations
I ran into an issue where I only wanted to show tours that were associated with the current logged in agency but wasn't sure how to dynamically do that. Probably not the best way but I'm sure the info can be useful for other things
```
let url = window.location.pathname.split('/')
const agency_id = url[2]
```
The first line lets you take in the url as a string and I split it on the "/" to get an array.
The agency id that I wanted was the [2] and I saved that under `agency_id`. 
Later when I wanted to filter out my Tours, I could show only those with an agency_id of what was in the url
		
