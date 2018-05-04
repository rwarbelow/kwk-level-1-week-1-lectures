## Sinatra Part 2

**NOTE:** This lecture involves more live coding/code explanation than others. Make sure you go through it ahead of time and practice!

## Objectives

Teach students how to create dynamic routes by parsing variables out of URLs. Additionally, teach students how to use dynamic routes to instantiate class instances and pass their variables to views, which will render the dynamic information. Following, quickly cover forms.

## SWBATS

- SINATRA: Incorporate models (Ruby Classes) into their applications
- SINATRA: Use dynamic URLs to instantiate models and return templated views
- SINATRA: Identify the use for post requests and forms

## Introduction

Having explored routes (responding to specific URLs) and views (returning erb templates) in the previous lecture, we will now turn our attention towards data models.

## Models

Models provide Sinatra applications with more structure by bringing object oriented programming into the framework. Just like we used Ruby classes and instances to organize functionality and data in our previous programs (recall the `Element` quizzer), we will use them to do the same in a Sinatra app. 

**NOTE:** You should take an active approach to walking students through the project linked below, which shows how to introduce basic models to a Sinatra app. 

https://github.com/learn-co-curriculum/kwk-l1-sinatra-periodic-table

We have a standard Sinatra app setup, which should look familiar to the students. This app has the new addition of models (located under the `models` directory). We also have a `rake console` task that will load our code into IRB so we can play with the objects outside of the context of the web app.

1. Open up IRB by typing `rake console` into bash when in the root of the project directory. Show them that our Sinatra code is loaded into the IRB session by instantiating a few elements from the `Element` class: 
  - `h = Element.new(1)` gives you an element of Hydrogen
  - `h.name` will give you the name, etc...
  
2. Follow up and show them the code of our model. Dissect the instance methods with the class and show them how instances only need an atomic number to look up their expanded element values in the class variable `@@TABLE`.

3. Fire up Sinatra now with `shotgun`.

4. Examine how the root URL displays an index of the elements, which can be clicked on. When a link is clicked, the URL changes to one designating a specific element. It's almost like there's a variable in the URL we want to capture!

5. Throw a `binding.pry` directly in your dynamic route in `application_controller.rb`. Refresh your Sinatra index page and click on one of the links. Following, your `binding.pry` will be triggered and you can step into the code in your bash terminal.

6. Try typing `params` and examine what prints out. Ask the students to explain what we are seeing. Emphasize the importance of this: we now have a dynamic route! We can parse out specific information from the URL, (in this case, "atomic_number"), and use that to inform the response we send back! Highlight the correlation between the route name with `/:variable` and the key we see in the `params` hash.

7. At this point, the students will break and do a coding exercise that uses this starter application. Make sure you are ready to troubleshoot questions. Students will likely have trouble creating an instance in their controller actions, as well as passing variables from these instances to be populated in their view. Remember: we should be, using the variable plucked out of `params` from the dynamic URL, creating a new instance in the controller action (don't forget to turn the string into an integer using `.to_i`). Instead of the static text that is rendering by default in our views, we should be loading text using `<%= >` tags and instance variables.

```ruby
element = Element.new(1) # won't be available in the erb template
@element = Element.new(1) # will be available in the erb template
```

## Code Exercise Deliverables (also listed in the repo's README)

- Render the element.html.erb template when the route is hit
- Instantiate an instance of the Element class via the dynamic route URL (in the appropriate controller action)
- Access instance variables in an action (a.k.a. the dynamic controller method) and pass them to the erb view template (note: variables must be prepended with an `@` to be passed between the controller action and the view!)
- Fill in the parts of that template that should be dynamic based on the instance they found in the controller
- Build out more instance methods for base_name and symbol, as it currently only has name and weight

**NOTE:** Stretch goals have been provided in the repo's README for students who are working particularly quickly. If they tackle the stretch goals, they should be prepared to take an active role looking up how to solve them on their own (using Google!). Your focus as an instructor should remain on getting all students through the base deliverables.

#### Once the Students Complete:

Go through and solve the deliverables with the students. Make sure to provide the solutions in real time, as if you were solving the challenge yourself. Do your best to describe your thoughts as you move through the list of deliverables -- the students learn from observing your method of problem solving. 

Students will now break for a personal site project.

**Break for Personal Site Project**
Spotify API: https://beta.developer.spotify.com/dashboard/applications
https://github.com/learn-co-curriculum/sinatra-personal-web-app


## Forms and Posting

**NOTE:** The periodic table Sinatra app repo we have been using has a specific branch for this section: https://github.com/learn-co-curriculum/kwk-l1-sinatra-periodic-table/tree/post-example. (You can switch to this branch on your command line by using: `git checkout post-example`). 

You will notice that, in addition to a solution for the previous deliverables, two additional views and routes are available. These new views and routes are used to both get a "make a new element" form, as well as return the result in HTML. The following should be walked through with the students:

1. Explain how we are going to make use of `POST` requests in our Sinatra app. This means we will be taking data from user submitted forms and doing something with it behind the scenes. Before, we were just looking up an element via a dynamic variable parsed out of a URL. Now, we will be taking in more data from a form and making use of it. 

2. Following, take a look at the new routes. Query the students as to what they think each does. One of them is to return the view that has the HTML form itself. The other one (the one marked `post`) is to digest the submitted forms information and then return the view that displays the results.

3. Dissect the HTML in each of the two new views. Ask the students how our `params` hash in our controller method gets the values (via the HTML tag's `name` attribute). Pay particular attention to the `<form>` attributes (`action` and `method`). Ask the students whether they are needed, and why/why not. 
