---
layout: post
title:      "learning PHP"
date:       2019-07-29 00:49:05 +0000
permalink:  learning_php
---


quick overview of what i learned about PHP.

this past week i received a PHP code challenge. so in addition to the actual code challenge, i had the additional challenge of learning PHP.<br>
i first started off by googling and read as much PHP documentation. for example, what the naming conventions are, what the code structure generally looks like, arithmetic operators, etc. some of the things that i've found out about PHP include:
* must end with semicolon or the code will break (unlike JavaScript where it's optional)
* script must start with ` <? php`, but best practices exclude the closing tag `?>` -- reasons being that excluding the closing tag to avoid unwanted whitespaces at end of file and be able to add headers to response
* variables start with `$`. for example, if i wanted to create a new variable called "hello," it would look like `$hello;`.
* new arrays used to be created with `$new_array = array( );`, but now can be created with brackets (`$new_array = [ ];`)
* `echo`, `print`, and `print_r` are used to output to console

