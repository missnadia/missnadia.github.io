---
layout: post
title:      "run-ins with the law"
date:       2019-03-04 22:51:59 +0000
permalink:  run-ins_with_the_law
---

i thought OmniAuth was bad...


**Murphy's Law**
"*anything that can go wrong, will go wrong*":

after months of grueling over trying to complete my Rails with JavaScript portfolio project, i'm happy to announce that i'm finally finished. the primary reason why this project took the longest time for me to complete was due to active_model_serializers ("ams") not running properly with my Rails project. i've spent countless amount of hours googling until i've exhausted my will to google another keyword, reviewed my notes and previous lessons, attended multiple study sessions targeting this specific project, and even had a 1 on 1 project session to no avail. eventually i ended up creating a lite version of my original Rails project to see if that would solve the issue and it did...until i had a run-in with another law.


**Hofstadter's Law**
"*it always takes longer than you expect, even when you take into account Hofstadter's Law.*"

now that i fixed the issue i was having with ams, i thought that it would be smooth sailing from there with a few bumps on the road, but instead it turned into a traffic jam with detours that kept bringing me back to the beginning. when i first read the requirements for this project, i had a general idea that it would take a bit longer than the Rails project due my lack of confidence in the AJAX component of the requirements, but not too long given that i was only adding a new feature to an already existing application.

WRONG.

turns out adding a new feature to replace or enhance part of an application that already exists is far more difficult than adding the feature to the application's original design (at least in this case). due to the fact that every piece of code has a functioning purpose in the application, i had to really understand the implications of what would happen if i added/removed a snippet of code otherwise my code would break without me understanding why. oftentimes the challenge was in locating these snippets of code playing hide-and-seek in another file. sometimes these snippets would camoflauge between usable code. in addition, i had to make sure my CSS styles were revised to include/exclude new/old class and id selectors to make sure the styles were applying correctly.

after refactoring and countlessly spamming my wombo combo--'binding.pry'/'debugger' and refresh page--to confirm that i'm using the correct selectors or that i was receiving the correct response from my AJAX requests, i still didn't learn my lesson.


**Pareto Principle/The 80-20 Rule**
"*roughly 80% of the effects come from 20% of the causes*" - meaning, 80% of the bugs come from 20% of the code.

i thought i got everything:
the jQuery selectors are grabbing the correct content.
i'm receiving the correct AJAX responses.
my variables are storing the correct data.

what's wrong????

turns out that when i removed one of the models, i didn't revise the model associations correctly. i also forgot to remove some of the obsolete attributes from the database and from the controllers.

...sigh.

a couple of words was standing in the way of completion. of course it's always something obvious.

if i had a penny for every time i underestimated the infamous laws of programming, i'd be rich.
let's see how many laws i break in my React portfolio project.


