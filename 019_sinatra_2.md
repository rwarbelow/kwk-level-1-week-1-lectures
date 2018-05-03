# # Sinatra Part 2

## Objectives

## SWBATS

## Introduction

**MVC**

So far we have controllers that define routes, which are URLs that we can access.

We also have templates of ERB

** Models **

Let's get some of our objects from OO into our sinatra app.

https://github.com/learn-co-curriculum/kwk-l1-sinatra-periodic-table

Walk them through the project, we have a standard sinatra app setup with the new addition of a models directly. we also have a `rake console` task that will load our code into IRB so we can play with the objects outside of the context of the web app.

Show them the usage of the `Element` class from the console, `h = Element.new(1)` gives you an element of Hydrogen, `h.name` will give you the name, etc...

So we have this functional model, let's fire up the sinatra app with shotgun

root shows index with a list of the elements. When you click on them notice what changes, the URL identifies the Element we want to know more about.

it's almost like there's a variable in the URL we want to capture.

show them params via `binding.pry` or `raise params.inspect`

explainb the dynamic route - the correlation between the route with `/:variable` and the key in the `params` hash.

Have them all open the lab at this point because they need to do the following.

BREAK FOR LAB

1. Instantiate an instance of the element via the dynamic route URL.
2. Render the `element.html.erb` template
3. Fill in the parts of that template that should be dynamic based on the instance they found in the controller
4. Build out more model methods for basename and symbol because it only has name and weight.

SHOW THEM HOW TO GET DATA FROM CONTROLLER TO TEMPLATE VIA INSTANCE VARIABLES

```ruby
element = Element.new(1)
```

wont appear availabe in the template you render. has to be

```ruby
@element = Element.new(1)
```

STRETCH
6. Can they do a find by name, like a URL `/element/hydrogen` requires a new model method, requires a new dynamic route, can re-use the element via, and requires a new navigational list. **Notice that they have to copy it over twice, leads to layouts, once in index and once in element**

Solve the lab with the students

SOLVE STRETCH GOALS

**COVER LAYOUTS FOR SHARED RE-USABLE COMPONENTS**

** More Routes **




** Dynamic Personal Site **

** Forms **

** POST Requests **

