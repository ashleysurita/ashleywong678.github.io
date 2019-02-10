---
layout: post
title:      "Know thy 'self'"
date:       2018-10-01 20:34:02 -0400
permalink:  know_thyself
---


Understanding "self" in Ruby was probably the hardest thing for me to grasp in Object Orientated Ruby. When learning about classes, I had no problem defining methods and variable for instances. But when we got to the topic of classes, that was #mindblown situation where it took me a lot of labs to understand.

The difference between 

`def add_song`

and

`def self.add_song`

not easy. Now, the way I remember it is this way:
Who owns the song? If we're talking about an artist and their songs, is that particular artist saying "Hey! Theses are my songs!" or are we talking in general where all artists are saying "Hey! All these songs have artists!" I find myself literally asking myself that when deciding who the method or the variable belongs to. Sometimes I still get it wrong, that's how confusing it is!

Although, I have found that the more practice you get in differentiating between the two, the more it makes sense for each lab that you complete. Believe me, I've had a lot of help along the way!

The easier part of self, is probably differentiating between the class variables and the instance variables. Not only because one has `@__` or `@@_`, but for me, the idea of what information belonged to the class compared to the instance was easier, a lot of the time they were related as well. 

For example:

```
class Cats

attr_accessor :name

@@all = []

def initialize(name)
   @name= name
	 @@all << self
end
```

Let's break it down...we have an **instance** variable `@name`, how do we know that the name should belong to the instance? What would make more sense, the single cat knows it's name or all cats ever created knows it's name?
Only a single cat is responsible for knowing its name! That's why `@name` is an instance and not a class variable. All cats in the universe aren't going to care about the next cat.
However, the cats class wants to keep track of all the cats created into the universe, Grumpy Cat isn't responsible for keeping track of all the other cats. That's why the `@@all` is a class variable and everytime we create a cat we `@@all << self` and add each cat instance to keep track.

I hope this helps you as much as the logic has helped me! Happy coding!
