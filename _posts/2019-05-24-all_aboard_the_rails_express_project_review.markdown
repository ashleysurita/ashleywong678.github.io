---
layout: post
title:      "All aboard the Rails Express (Project Review)"
date:       2019-05-25 01:28:44 +0000
permalink:  all_aboard_the_rails_express_project_review
---


Looking at the final product and seeing where I was when I started, I realize I've come a long way. Tihs project has had a lot of complexities in the file tree and structure in how it's set up. To get started, I have to say I relied heavily on the [Ruby on Rails Guide](https://guides.rubyonrails.org/getting_started.html) to get me through, they had great step by step instructions in getting the basic file structure started. 

Similar to Corneal app for Sinatra, this app really alieviated by anxiety about making sure I had the basics included. I also found it a lot easier to build my controllers, models, views, and tables myself, the one time I used scaffolding it was a little overwhelming to comb through all the files. 

The one thing that was daunting to me but I began to feel more comfortable with after going to many study groups was using nested routes. Once it 'clicked' and I fully understood how it worked, I find it kind of useful, expecially when making relationships between objects. The nested forms however are still tricky, but still useful.

The toughest part of my project is my join table. I had tried everything I could to avoid an additional join table that was not a conceptual object but wasn't able to find one. My schema and relationships ended up being like this:

Agency has_many => <= belongs_to Tours 

Tours has_many => <= belongs_to Customer_Tours (join table) belongs_to => <= Customers

The Customer_Tours table and it's additional attribute was the difficult part that I struggled with. At first, the support coach and I decided on additing "notes" where an agency can add notes about a trip. However, getting it to update and render correctly was difficult. Also adding it to the create and update actions was a **NIGHTMARE**. Another coach gave me an idea for a boolean, that turned out to be tough also but more workable. I ended up creating a button for that which sends an update to the controller and redirects to the original page. 

Another thing that was challenging was figuring out the google-oauth2 and setting it up. I think many students use FaceBook because it's in the example lab so it's easy to follow along with it. But I don't have FaceBook! And it wouldn't make sense to login with GitHub for a travel agency, so Google ended up making the most sense. There are so many tutorials and they each have a different set of instructions which made it hard to know how to do it correctly or what I was even doing. Most of the time, I honestly copied and pasted as it told me to without understanding the steps (there weren't many explanations). I eventually worked with help from some others. Now that I know what to expect, I think that the Google Oauth is much more useful and I'll probably be needing it again.

The part I found most enjoyable was styling my app. There aren't as many opportunities to use HTML and CSS so far in the lessons and surprisingly there are a lot of good tutorials and free styling. I had tried using bootstrap like others and loaded it to my app, but honestly didn't really know how to get the styling done. However, putting some SCSS into my app turned out to be a lot easier then I expected, and playing around with the different formats and attributes was enjoyable. I probably spent WAYYYY too much time on it though, it probably pushed me back at least 2 days in finishing when I could have done it at the end.
