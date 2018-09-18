---
layout: post
title:      "< Code > Lyfe of OO"
date:       2018-09-18 00:14:00 +0000
permalink:  code_lyfe_of_oo
---


The great part about ruby is that it uses the concept of Object Orientation (OO for short), but how does that help us to code? Object orientation is the idea that everything in code is represented as an *"object"* and we manipulate them with our code. Why is this important? It helps us as developers to understand code in the way that we understand real life. For example, image  a cup in real life. Now, in code, we can create a cup:
```
cup = "cup"
```
Now, when we want to call on our cup, it will return 'cup'. We have just declared that the variable cup, will return the string "cup" and thus represents the word cup.

This is helpful for us particularly when we use classes in OO. There, we can create a category and give it properties or attributes, just like the real world. For example: 
```
class Dog

end
```
We have now created a category called `Dog` (important note: classes are always captialized which helps you know it's a class). Now if we want to create a dog, we can in our terminal by writing:
```
>Dog.new
=> #<Dog:0x000055e2794f68f0>
```
We can treat this like a real dog! Our new dog has been created and has been given a certain ID number so our program can find it later. We have now created a dog! But what if we want to give it a name? Or a breed?, Or it's age? Just like it real life, we will have to give it those attributes by defining them:
```
class Dog

#1st method
def name=(name)
  @name = nme
end

#2nd method
def name
  @name
end

end
```
To break it down, the first method defines our new **instance** variable, called name=. This means that for our dog, we can use this variable at anytime within the Dog class. This is called the *writer* or *setter*, I differentiate it from our next method because it "sets" our variable's value.

Our next method is called the *reader* or *getter* method. This method allows the user to retrieve the variable's value and read it after it has been set. Without it, we would not be able to have the program tell us what the variable's value is!

We also want to give our dog it's name when it's born. To set a variable's value when creating a class instance, we use a method called the **initialize** method (note: the *@* symbol will indicate to us that the variable is an instance variable):

```
class Dog

def initialize(name)
  @name = name
end

def name=(name)
  @name = nme
end

def name
  @name
end

end
```

Now we can give our dog a name!
```
>Dog.new("fido")
=> #<Dog:0x00005610e26ba370 @name="fido">
```

Us programmers are lazy, and if we had to write all of that everytime, our code would like ridiculously long! So to reduce the amount of typing, we can use an `attr_accessor` which combines the *setter* and *getter* which will work the same as the above code:
```
class Dog

  attr_accessor :name

def initialize(name)
  @name = name
end
```
So much nicer looking! You can add multple attributes by separating them with a comma:
`attr_accessor :name, :breed, :age` etc...
