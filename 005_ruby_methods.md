# Ruby Methods - Full Lecture

## Objective
+ Students will be able to create and use methods with arguments.

## SWBATS

+ METHODS - explain what a method is and why it's used
+ METHODS - use built in methods for each data type and structure
+ METHODS - chain methods together
+ METHODS - experiment and investigate unknown ruby methods using documentation and other 
+ internet resources
+ METHODS - explain what a return value is and what it's used for
+ METHODS - explain and determine the return value of a method
+ METHODS - explain what the return value of the puts method is
+ METHODS - differentiate between methods that puts and methods that return a value
+ SCOPE - explain that local variables cannot work between methods because of scope
+ METHODS - explain the difference between defining and calling a method
+ METHODS - call previously defined custom methods
+ METHODS - create a custom method using def and end key words
+ METHODS - use correct syntax in naming methods
+ METHODS - create a custom method using arguments

## Motivation

We left off yesterday looking at methods. Methods allow us to name a sequence or selection of code and run it whenever we want.

Let's play with a `greeting` method in IRB **Students should follow along in IRB**

```ruby
def greeting
  puts "Hi Jane, I'm Karlie, how's your afternoon?"
end

greeting
```

We mentioned that the data in that method really has 3 variables embedded in it and if we wanted to make the method more flexible, we'd need something like:

`local_greeting` might be "What's up", or "Hey", or "Yo", or "Konichiwa"

`your_name` might be "Alice" or "Shirley"

`my_name` might be "Grace" or "Katherine"

`time_of_day` might be "morning" or "night" or "afternoon"

We might be able to use variables for this, let's try it, in IRB, students following along.

```ruby
local_greeting = "Shalom"
your_name = "Golda"
my_name = "Lea"
time_of_day = "life"

# The goal being to get a greeting of:
#> "Shalom Golda, I'm Lea, how's your life?"

def greeting
  puts "#{local_greeting} #{your_name}, I'm #{my_name}, how's your #{time_of_day}?"
end
```

As we saw yesterday, that doesn't work. The reason why is an important programming concept called **scope**

Variables have a locale, a place where they exist. We call the place in which a variable exists a "scope."

**NEED GOOD SCOPE METAPHOR OR EXAMPLE - SOMETHING THAT EXISTS IN DIFFERENT PLACES, IS CALLED THE SAME, BUT GETS ITS OWN DEFINITION**

Because of variable scope, a method only have access to information defined within it. We could do the following:

```ruby
def greeting
  local_greeting = "Shalom"
  your_name = "Golda"
  my_name = "Lea"
  time_of_day = "life"
  
  puts "#{local_greeting} #{your_name}, I'm #{my_name}, how's your #{time_of_day}?"
end
```

But now that `greeting` method is very specific, we wouldn't be able to change it to say hello in a different way to a different person.

## Arguments - 10 Minutes

Lots of times in programming we can imagine "the code we wish we had." What I'd really want to be able to do is something like:

```ruby
greeting("What's up", "Kim", "Kanye", "morning")
#> "What's up Kim, I'm Kanye, how's your morning?"
```

We want to be able to pass the information into the method, sort of like a fill-in-the-blank madlibs, and have the method use those values. That would allow us to keep the method the same, but change the data it uses.

```ruby
greeting("What's up", "Kim", "Kanye", "morning")
#> "What's up Kim, I'm Kanye, how's your morning?"
greeting("Hey", "Beyonce", "Karlie", "night")
#> "Hey Beyonce, I'm Karlie, how's your night?"
```

Let's actually try that - **have students define the base greeting method and then try to call it with those arguments, it will break, but that's good**

```ruby
def greeting  
  puts "#{local_greeting} #{your_name}, I'm #{my_name}, how's your #{time_of_day}?"
end

greeting("Hey", "Beyonce", "Karlie", "night")
```

You will get: `ArgumentError: wrong number of arguments (given 4, expected 0)`

Give the students 5-10 minutes to google `ruby method arguments` ruby and see if they can figure it out.

Results they should see in google:

https://learn.co/lessons/methods-default-arguments
https://www.skorks.com/2009/08/method-arguments-in-ruby/
http://codeloveandboards.com/blog/2014/02/05/ruby-and-method-arguments/
https://ruby-doc.com/docs/ProgrammingRuby/html/tut_methods.html
https://www.crondose.com/2016/09/comprehensive-guide-to-method-arguments-in-ruby/

**Ask if anyone got it working and can explain it to the class**

Continue to official explanation. 

Arguments allow us to pass data into a method. They are sort of like protein-transfer receptors [Protein Transfer](http://nat5biopl.edubuzz.org/_/rsrc/1359400919033/unit-1-cell-biology/2-transport/IMG_0090.JPG?height=310&width=600) [Transport](http://nat5biopl.edubuzz.org/unit-1-cell-biology/2-transport). In the same way a Cell is a self-contained thing that has to take things from the outside world, a method is like that too.

Let's simplify the `greeting` method (point out that it's always good to start with the simplest example when learning something new) and play with arguments.

In the method signature, the `def` line, when defining a method name's, you can attach arguments. In `irb`, everyone play along.

```ruby
def greeting(my_name)
  puts "Hi, I'm #{my_name}"
end

greeting("Cardi B")
#> Hi, I'm Cardi B
```

Arguments go in parenthesis and just like variables, you can name them whatever you want. The name you use to define the argument will be the local variable inside the method that the piece of data will be referenced as.

```ruby
def greeting(my_name)
  puts "Hi, I'm #{my_name}"
end

greeting("Cardi B")
greeting("Fergie")
greeting()
```

Oh oh, once we define a method to have an argument, you have to call it with that argument, otherwise Ruby will throw an `ArgumentError`. You get an `ArgumentError` for sending arguments when a method doesn't accept them or not sending arguments when a method requires them.

You can define multiple arguments with `,` in the method signature.

```ruby
def greeting(my_name, your_name)
  puts "Hi #{your_name}, I'm #{my_name}"
end

greeting("Cardi B", "Karlie")
greeting("Fergie", "Karlie")
```

You don't have to send literal data, like a literal String as a value for an argument, you can send references (variables)

```ruby
def greeting(local_greeting, your_name, my_name, time_of_day)
  puts "#{local_greeting} #{your_name}, I'm #{my_name}, how's your #{time_of_day}?"
end

a = "Shalom"
b = "Golda"
c = "Lea"
d = "life"

greeting(a,b,c,d)
```

**Method Argument Labs** 20 Minutes Max

[Parrot Methods]<!-- (https://github.com/learn-co-curriculum/kwk-l1-parrot-methods-lab) -->
[Cell Transport Methods Lab]<!-- (https://github.com/learn-co-curriculum/kwk-l1-cell-transport-methods-lab) -->
[Geometry Formulas Methods Lab]<!-- (https://github.com/learn-co-curriculum/kwk-l1-geometry-formuals-methods-lab) -->

## Default Arguments - 5 Minutes

Let's go back to our `greeting` method. There's a lot to specify in there. We have to pass 4 arguments every time! What if we wanted to make some things a default, so if we don't specify something, the method can still work? Let's start with a simplified example

```ruby
def greeting(my_name, my_greeting)
  puts "#{my_greeting}! I'm #{my_name}"
end

greeting("Karlie", "Heyyyyyy")
```

So two arguments. What if we wanted to say that by default, `my_greeting` should just have a value if we don't send one explicitly (what's that word mean?)

Want to try googling it? **Give students a chance to google ruby default arguments** 5 Minutes. Have someone explain the default argument.

If you want an argument to have a default value, you just assign the default when you declare the argument. 

```ruby
def greeting(my_name, my_greeting = "Hi")
  puts "#{my_greeting}! I'm #{my_name}"
end

greeting("Karlie") #> Hi! I'm Karlie
greeting("Cardi B", "Heyyyyyy") #> "Heyyyyyy! I'm Cardi B"
```

We tend to keep our arguments with defaults last, anyone want to guess why?

**Default Argument Labs** 15 minutes

[Say Hello]<!-- (https://github.com/learn-co-curriculum/kwk-l1-say-hello-methods-ruby) -->
[Meal Choice]<!-- (https://github.com/learn-co-curriculum/kwk-l1-ruby-2-meal-choice-lab) -->
[Mother’s Day]<!-- (https://github.com/learn-co-curriculum/kwk-l1-mothers-day-methods) -->
