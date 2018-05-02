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
```

In this case, '/spaghetti', '/sushi', _and_ '/' are the specific paths within the site. If there isn't anything after the the base URL, the path is equal to '/'.

All we need to worry about though

Writing a route look very much like the _Ruby methods_ we just learned about.

### #STILL WORKING - Max
A

```ruby
get '/' do
  "Hello World"
end
```

a route with a dynamic response

```ruby
get '/random' do
  "#{rand(1..100)}" # Picks a number from 1 to 100
end
```

But if we wanted a bunch of HTML

```ruby
get '/random' do
  "<h1>Hello!</h1><h2>The time is #{Time.now}</h2><p>#{rand(1..100)}></p>" # Picks a number from 1 to 100
end
```

thats not going to work

so we have templates

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/controllers/application_controller.rb#L9

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/views/index.html.erb

Cover ERB <% %> and <%= %>

If we return HTML,

That's sinatra basics

**HELLO WORLD LAB**

https://github.com/learn-co-curriculum/kwk-l1-sinatra-organizer
https://github.com/learn-co-curriculum/kwk-l1-sinatra-hello-world-basics (would love to this to mirror the structure from MVC in the starter as we'll never use app.rb in this course)
