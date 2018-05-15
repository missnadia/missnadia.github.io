---
layout: post
title:      "what is object oriented programming?"
date:       2018-01-18 16:16:59 -0500
permalink:  common_programming_paradigms
---

common programming paradigms

every programming language is characterized by one or more programming paradigm. a programming paradigm is simply a way to classify a programming language based on its functionality and characteristics.

one common programming paradigm is called object oriented programming (OOP) (a familiar term on the lessons covering OO Ruby). OOP is a programming paradigm that is modeled around combining the data and functionality of a program into an object.

in OOP, all of the objects to be manipulated and their relationship to each other are identified (data modeling) and then grouped into a *class* that contains all of the data and any functions (methods) of that data that manipulate it. for instance, if you define a class called residence, an object of that class would be a house. a house would then have additional objects (doors and windows) that each has its own function (open/close), but serve the overall function of a house -- provide residence.

the function of the house is inherited by the objects of the house (doors and windows), allowing some or all of the properties and behaviors of the parent object (residence) to become part of each subclass. this allows reusability of data without having to create new code if you wanted to create a new subclass called apartment.

because the data of the objects in OOP is predefined in its associated classes, data that is not associated with the object or its parent class cannot modify the code or be accessed (data hiding). for example, if i created a new class called desserts with an object called ice cream, i would not be able to access the data in my class called residence.

languages that are classified under this paradigm are:

* Python
* Ruby
* Scala
* Smalltalk
* Eiffel
* Emerald
* JADE
* Self
* Java
* C++
* C#
* Object Pascal
* VB.NET

