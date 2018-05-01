# Sinatra Part 1

## Objectives

## SWBATS

## Introduction

**Sinatra is a Ruby Application that can respond to HTTP Requests**

- It's a program that's always on once started, it's sitting waiting for web requests
- you start your sinatra application with `shotgun config.ru`
- `config.ru` is a ruby file that tells Sinatra how to run your application.

** Starter Sinatra Application **
Use [KWK Sinatra Starter](https://github.com/learn-co-curriculum/kwk-sinatra-starter)

**Students should open [KWK Sinatra Starter](https://github.com/learn-co-curriculum/kwk-sinatra-starter) in the Sandbox or we make it into a lab so that we can walk through it**

**Everyone type in shotgun and go to the IP address of your server**

**Hit refresh a few times, notice it changes the content everytime, that's because ruby is processing this request everytime and can dynamically generate a response**

Let's follow the flow of how this program started

First, config.ru
https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config.ru

Environment
https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config/environment.rb

gets all our code loaded into memory (not sure we've covered gems/bundler but we should, they are super powers you can inherit, like the entire Sinatra source code)

https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/app/controllers/application_controller.rb

That's going to be what creates different "pages" for our application

Once we have all that code loaded, let's go back to config.ru, because none of it is being run yet

the key line https://github.com/learn-co-curriculum/kwk-sinatra-starter/blob/master/config.ru#L3

`run` is Sinatra, it says, hey, use this class as the object that has all the logic for our web application. with that the application starts.

When we make a request, Sinatra looks for a matching "route" in ApplicationController

a route

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

That's sinatra basics

**HELLO WORLD LAB**

https://github.com/learn-co-curriculum/kwk-l1-sinatra-organizer 
https://github.com/learn-co-curriculum/kwk-l1-sinatra-hello-world-basics (would love to this to mirror the structure from MVC in the starter as we'll never use app.rb in this course)


