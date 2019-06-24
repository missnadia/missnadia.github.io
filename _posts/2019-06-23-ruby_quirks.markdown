---
layout: post
title:      "Ruby quirks"
date:       2019-06-24 00:41:58 +0000
permalink:  ruby_quirks
---


reviewing Ruby.

advantages of using Ruby:
* pure object-oriented language
* open-source
* metaprogramming
* clean and simple syntax

types of variables:
* global (`$variable_name = "Hello"`)
* local (`variable_name = "Hello"`)
* class (`@@VARIABLE_NAME = "Hello"`)
* instance (`@variable_name = "Hello"`)

blocks v. procs v. lambdas
* blocks - not an object, but code used by methods
* procs - object; does not check number of arguments
* lambdas - object; checks number of arguments
