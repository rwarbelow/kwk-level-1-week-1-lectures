# Sinatra Part 1

## Objectives

Students will dive in to Sinatra and practice generating web content using a
route written in Ruby.

## SWBATS

- Practice serving basic web pages from different routes on the same app
- Understand how Ruby allows us to handle dynamic information and serve it on
request

## Introduction

**Sinatra is a Ruby Application that can respond to HTTP Requests**

- It's a program that's always on once started; it's sitting waiting for web requests
- Start your Sinatra application by running `shotgun config.ru` in the terminal
- `config.ru` is a Ruby file that tells Sinatra how to run your application.

** Starter Sinatra Application **
Use [KWK Sinatra Starter](https://github.com/learn-co-curriculum/kwk-sinatra-starter)

**Students should open [KWK Sinatra Starter](https://github.com/learn-co-curriculum/kwk-sinatra-starter) in the Sandbox or we make it into a lab so that we can walk through it**

**Everyone type in shotgun and go to the IP address of your server**

**Hit refresh a few times, notice it changes the content everytime, that's because ruby is processing this request everytime and can dynamically generate a response**

Let's follow the flow of how this program started

First, `config.ru` runs
https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config.ru

In `config.ru`, `environment.rb` is called when it is required
https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config/environment.rb

The `environment.rb` file gets all our code loaded into memory. We haven't
covered gems/bundler, but in short, they are super powers you can inherit, like
the entire Sinatra source code, in this case.

Once we have all that code loaded, we jump back to `config.ru`, because none of
that code is being run yet. Back in `config.ru`, _ApplicationController_ is run
on line 3:
https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config.ru#L3

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/controllers/application_controller.rb

The ApplicationController is going to be what creates different "pages" for our
application. On line 3 of `config.ru`, the word `run` on is Sinatra; it says,
'hey, use this class as the object that has all the logic for our web
application.' And with that... _our application starts._
### Building Routes to Content

Again, Sinatra, in essence, is a Ruby app that, when started, will start
listening for HTTP requests.  When a request is received, ApplicationController
is checked for a matching _route_.  In the starter code students have, when they
enter the IP they were given into the URL bar, their app _heard_ the request,
went to the ApplicationController and looked to see if the request matched
anything

### Cooking Up Some Content

Imagine you're the new chef of a fire star restaurant, and orders are coming in!
You're still pretty new, but luckily, you've been given a book of instructions
on how to make each meal a customer can order.

Each order comes in on a small slip of paper and says something.. one order says
`spaghetti`, another says `veggie burrito`, and another says `sushi`.  You get
the requested order, go and look in your book, find the matching instructions,
cook the meal, arrange the food and send the plate out.

If I **get** `spaghetti`... find and follow the instructions for `spaghetti` and
send out a plate when done If I **get** `cheeseburger`... find and follow the
instructions for `cheeseburger` and send out a plate when done

Sinatra routes work similarly... If Sinatra _gets_ a request for `something`, it
looks for instructions for that `something`, and if found, follows them,
returning whatever it has put together.

The `something` is the specific path requested within a site; everything on the
URL that immediately follows the base site URL:

```
www.new-chef-in-five-star-restaurant.com/spaghetti
www.new-chef-in-five-star-restaurant.com/sushi
www.new-chef-in-five-star-restaurant.com/
159.203.187.180:8080/spaghetti
localhost:3000/sushi
```

In this case, '/spaghetti', '/sushi', _and_ '/' are the specific paths within the site. If there isn't anything after the the base URL, the path is equal to '/'.

## Writing the Recipe Instructions

Sinatra knows what to do, its a good cook, we just need to give it the
instructions - if our application _gets_ `/sushi` or `/` or `/about_page` we
need to tell Sinatra to what to do in response:

```ruby
get '/' do
  "Hello World"
end
```

Huh... writing these instructions looks very much like the _Ruby methods_ we
just learned about! In the above example, if our app _gets_ a request for `/`,
it returns "Hello World".

We can make as many of these as we like..

```ruby
get '/spaghetti' do
  "Hello Spaghetti"
end

get '/sushi' do
  "Hello Sushi"
end
```

And if our Sinatra app _gets_ a request for any of these, it will match our
instructions and return the correct text!

 [Hello World
Lab](https://github.com/learn-co-curriculum/kwk-l1-sinatra-hello-world-basics)
(would love to this to mirror the structure from MVC in the starter as we'll
never use app.rb in this course)

## Dynamic Responses

Okay, going back to the new chef metaphor.. you're doing great, following the
cooking instructions, but the owner has decided to expand the menu a bit.  They
want an _surprise_ special. If a customer orders the `special`, they will get a
different meal every time.

As the chef, when you get these orders, you look at your instruction book and it
says:

```
mix random things together on a plate.
```

...and so you do. One customer gets spaghetti car_banana_, another gets spicy
peanut butter, and another gets ice cream filet of shoe sole.  This is a dynamic
response.  You don't always get the same thing!

Okay, how does this relate to Sinatra? Well, we do something similar: we can
write instructions for what to do, but those instructions _may not be set in
stone_.  We could change them as we see fit.. change the response depending on
the time of day, or return the current time. We could make the response
_random_.

We just need to give the instructions, and Sinatra will follow them.  Writing a
route with a dynamic response in Sinatra looks like this:

```ruby
get '/random' do
  "#{rand(1..100)}" # Picks a number from 1 to 100
end

get '/current_date' do
  Time.now().strftime("%c") # Gets the current time and date, converts it to string format
end
```

## Return HTML

So far, we've got Sinatra sending single lines of text in resposne to requests,
but what if we wanted a bunch of HTML, instead?

```ruby
get '/random' do
  "<h1>Hello!</h1><h2>The time is #{Time.now}</h2><p>#{rand(1..100)}></p>" # Picks a number from 1 to 100
end
```

Thats not going to work. We've seen HTML, too. We wouldn't want a whole HTML
page listed out like this.. it would be impossible to read.

Instead of serving up strings, like we've done so far, Sinatra can serve up
_files_.

Back on our Sinatra starter code again:

In our ApplicationController:

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/controllers/application_controller.rb#L9

We've got a familiar looking `get` route here, but instead of returning a
string, we've got `erb: 'index.html'`.

In a nearby folder, `app/views/`, we have a file called `index.html.erb`:

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/views/index.html.erb

This is how Sinatra serves up whole webpages. Using ERB files (embedded Ruby),
we can write HTML just as we were doing earlier this week, and have Sinatra serve
them at specific routes.

## ERB <% %> and <%= %>

We've got one more thing to talk about.  On `index.html.erb`, there is something
new that we haven't seen yet.

There is _Ruby_ inside of our HTML! The `rand(1..100)` and `Time.now().strftime("%c")` methods we saw earlier when talking about dynamic responses... are _inside_ our HTML content.

We do this with ERB! Any time we want some dynamic content 

If we return HTML,

That's sinatra basics

**HELLO WORLD LAB**

https://github.com/learn-co-curriculum/kwk-l1-sinatra-organizer
