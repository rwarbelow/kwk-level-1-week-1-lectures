# Introduction to Ruby

## Objective

Students will be able to use ruby's basic data types to make a simple command line application that manipulates data.

## SWABTS

+ GENERAL RUBY ‐ explain that all programs are just lines of text read by a computer
+ GENERAL RUBY ‐ demonstrate that ruby programs read top to bottom
+ GENERAL RUBY ‐ differentiate between data and key words
+ STRINGS ‐ explain what a string is and why it's used
+ STRINGS ‐ create strings using double quotes
+ STRINGS concatenate two strings using the +
+ STRINGS ‐ use common string methods
+ PUTS ‐ Explain what putsing is and what it's used for
+ INT ‐ explain what an integer is and why it's used
+ INT ‐ use common mathematical operations with integers
+ INT ‐ understand that ruby rounds down when doing math with integers
+ INT ‐ use typical methods like to_f and to_s to mutate integers
+ FLT ‐ explain what a float is and why it's used
+ FLT ‐ understand that math with floats produces floats and math with integers produces integers
+ FLT ‐ use typical methods like to_i and to_s to mutate float
+ FLT ‐ use common mathematical operations on floats
+ STRINGS/VARIABLES ‐ interpolate a variable or a method within a string
+ VAR ‐ use a variable in place of a piece of data
+ VAR ‐ assign integers to variables
+ VAR ‐ assign floats to variables
+ VAR ‐ reassign the value of a variable
+ GETS ‐ take in user input using the gets method
+ VAR ‐ use correct syntax in naming variables
+ GENERAL RUBY ‐ predict that the effect of text in ruby that is not data or a key word will throw an error
+ GENERAL RUBY ‐ explain that an error will stop the execution of ruby code

## Motivation

Introduce Ruby by talking about amazing things that have been built with it: AirBnb, Twitter, Groupon, SoundCloud...

Ruby is a backend programming language that is typically used to build **web applications.**

Explain backend with example of website vs. web application. A static site for a pizza parlor shows the same info to everyone who visits - telephone number, location, etc. - but when you log into a site like Facebook you get a unique experience. It knows who you are and who your friends are. It also lets you, and only, connect to new friends, upload photos, update your status, etc. A backend is what makes this possible.

Ruby is an awesome backend language because easy to read, easy to learn, and there are a ton of resources available.

By the end of this lesson you will be able to build a small program that takes in input and gives you an output.

## Your First Program: Hello, World

All programs are just lines of text read by a computer. We're going to create a ruby file, which is just a file written in a text editor with the file extension `.rb`.

**Have students Open [Hello, World]<!-- (https://github.com/learn-co-curriculum/kwk-l1-hello-world) --> in the IDE**

Now let's make a ruby file `touch hello_world.rb` and open it by double clicking it in the file navigator.

This empty text file is where we're going to write our code that the program will execute later. We're just going to be writing instructions for the computer to know what we want it to do, and then later we can tell it to actually follow the instructions.

Students should type `puts "Hello World"` into `hello_world.rb`.

Have the students run the program by running `ruby hello_world.rb` in their terminal.

Every programmer starts with a program that outputs hello world. congratulations, you're all developers now. WOOO CLAP!

Let's run the tests and see if this code meets the requirements of the lab.

Have the students type `learn`

They will see:

```
Failures:

  1) Hello World puts "Hello World!"
     Failure/Error: load './hello_world.rb'
     
       #<IO:<STDOUT>> received :puts with unexpected arguments
         expected: ("Hello World!")
              got: ("Hello World")
     # ./hello_world.rb:1:in `puts'
     # ./hello_world.rb:1:in `<top (required)>'
     # ./spec/hello_world_spec.rb:10:in `load'
     # ./spec/hello_world_spec.rb:10:in `block (2 levels) in <top (required)>'
```

Tell students it is okay for things to be broken, the normal state of all programs are broken, if their code worked, they'd be done. 

Errors are our friends, they tell us what is wrong. Can anyone read the error and figure out what's wrong?

This lab expected "Hello World!" and we only printed "Hello World". Lets fix that. Run `learn` again and it all works. Tell the students to submit the lab with `learn submit`.

## Commands, Data, and Code

We have two important pieces to keep in mind - data and key words. All programs are made up of these two things. In this example, puts is a command and "Hello World!" is a piece of data called a string.

What is data? (ask class for their thoughts). The internet is entirely made up of data and websites give context for that data. Fandango is a website for movie information, but without knowing what Fandango is and does, it's just a bunch of random addresses, names, and times on the screen. That's data and Fandango gives context for it.

What is a string? Strings are a piece of data denoted by double quotes. A string can hold any type of character, letters, numbers, spaces, and all special characters like !!!&&&. It's used to hold information in a sentence-like format. We have to put the double quotes for the computer to treat the sentence as data. As people, we look at words written and automatically know that they are words to be read and contain information. Computers are stupid and have to be told explicitly what they are. Any time you type a new Facebook status, or comment on a friend's Instragram, the backend code of those applications reads those posts as Strings.

***(Pause for students to explain to a partner what a string is)***

And `puts`? `puts` is an action built into Ruby that tells the computer to print out your piece of data to the screen. It's telling the computer, show this information to my user. It stands for output string.

Let's play with some examples of commands, data, and code.

Have the students type `irb` from the Open IDE from the Hello World lab or open their `Learn` Sandbox. 

From `irb`, explain that this is a Ruby command prompt where they can execute valid Ruby. Try `1+1` and press enter.

```
// ♥ irb
2.3.1 :001 > 1+1
 => 2
```

They will see `2` as the return value. Have them exit `irb` by typing `exit`.

``` 
2.3.1 :002 > exit
```

Back at their Command Line, have them try `1+1`

```
[19:03:49] (master) kwk-l1-hello-world
// ♥ 1+1
-bash: 1+1: command not found
```

Bash doesn't understand Ruby, only Ruby does. Let's go back into `irb`. Have them type "1+1" with quotes, as a string.

```
[19:03:52] (master) kwk-l1-hello-world
// ♥ irb
2.3.1 :001 > "1+1"
 => "1+1"
```

Can anyone explain why ruby treats `1+1` with no quotes differently than `"1+1"` with quotes?

That's code vs data. Ruby ignores data and only evaluates or translates or interprets code. Strings are data.

From `irb` continue by allowing the students to `puts` any sentence they want, similar to `"Hello World`

```
2.3.1 :001 > puts "Programming is awesome!"
Programming is awesome!
 => nil 
```

Notice it printed `Programming is awesome!` and returned `nil` which we will talk about later.

Strings can do a lot of things. Let's explore some things strings can do:

From `irb` demo:

+ `.length`
+ `.reverse`
+ `.upcase` `.downcase` `.swapcase`
+ `.capitalize`

+ You can even chain methods together: `"hello world".upcase.reverse.capitalize`

### String Labs - 15-20 minutes

Have students work on [String Interactive Practice]<!--(https://github.com/learn-co-curriculum/kwk-l1-strings-mini-lab)--> (This must be loaded in Learn) 

Students can also begin work on [Silly Strings]<!-- (https://github.com/learn-co-curriculum/kwk-l1-silly_string/) -->

Review String Interactive Practice with students, solve the start of Silly Strings so that during lab time they have already started.

## Math and Ruby

So what does: puts `"1" + "1"` give us (it is "11")? That's definitely not the correct answer, so how do we do math in ruby? We need integers! integers are another data type in ruby.

In `irb` play with math with the students.

What is an integer? ask students it's just a whole number

```ruby
1 + 1
10 - 1
10 * 10
100 / 2
100/3
```

Why do we get 33? math with integers produces integers and ruby typically rounds down when doing math with integers? PEMDAS applies

So how do we get decimals? In Ruby (and programming in general) they're called floats. A math problem with one float in it will produce a float

`100 / 3.0`

What happens if we do `"100" + 100?` We get an error because they're different data types. Ruby won't let us add an integer to a string

We can convert  data types with methods called `to_i`, `to_f`, and `to_s`

```ruby
"100".to_f
"10".to_i
100.00.to_i
```

***Let students do math with floats and convert diff data types in pairs***

## Variables

Who here has taken algebra before? ***Ask students what a variable is.*** We use variables in programming to store pieces of data. Variable names contain all lowercase letters. 

In `irb` play with:

```ruby
a = 1
b = 2
a + b
```

Apps use variables to store data they take in from their user to clean it up (data sanitation - like the `downcase` method) before they save it to the database.

Variables can store all types of data, including strings:

```ruby
name = "Vanessa"
puts name
```

Notice we're not typing `puts name = "vanessa"` but Ruby is actually doing that variable assignment. It's doing it behind the scenes so when we type puts name, it gives us "Vanessa"

***Students create 3 variables: 1 with first name, 1 with last name, 1 with age***

Variable reassignment: What happens if we do `name = "danny" puts name`? 

We reassigned the value of the variable

We can't have spaces in our variable names. what happens if we did?:`last name = "danny"`

error! ruby doesn't know what 'last' is. It's not data, it's not a keyword. It doesn't know what it is, so it throws an error. Notice the error stopped the execution of our program. 

ERRORS AREN'T BAD!!!!! they're breadcrumbs to your problem. Ruby is telling us exactly what part of our code it doesn't understand.

***students do it too***

### Variables Lab - 10 minutes

Have them do [Variable Interactive Practice]<!-- (https://github.com/learn-co-curriculum/kwk-l1-variables-mini-lab) --> in Learn.

Then have them work on [Variable Assignment Lab]<!-- (https://github.com/learn-co-curriculum/kwk-l1-variable-assignment) -->

## Interpolation

In IRB

```ruby
name = "Karlie"
age = 25

puts "My name is " + name +  " I am " +  age.to_s + " old"
```

Buildings strings like this with variables is annoying. There has to be an easier way to do this. That's a lot of plus signs and keeping track of spaces..interpolation to the rescue!

`"My name is #{name} #{last}. I am #{age} old."`

Interpolation is denoted with the hashtag and curly braces. Between the two curly braces, our computer knows to execute ruby code. it will actually output the value stored in the variables name, last, and age instead of printing out the words name, last and age.

We said at the start we were going to make a little program by the end of this lesson. Programs usually take in information, do something to it, and then output that mutated information. We've learned how to do something to information, and how to output it, but how do we take it in? 

A little method built into Ruby called `gets`:

demo a program `whats_your_name.rb`: 

```ruby
puts "What is your name?" 
gets
```

Run the program. Notice terminal hangs to let us type in input, but then it doesn't do anything with it. we need to be able to persist/store our input. ***What have we learned about that lets us store data?*** variables!! 

```ruby
puts "What is your name?" 
name = gets 
puts "Hello #{name}!"
```

## Conclusion 

Web applications follow and input-output pattern. You input a comment to the funny cat meme your friend put on Facebook, and it's outputted back to you in Facebook's pretty format. This structure is the basis of every application, and you just learned how it works.

## Hints and Hurdles

`gets` takes in all information as a string and with the newline-character at the end of it. add `.strip` to get rid of the newline.

## Labs to Work On

+ [Messy Macarena]<!-- (https://github.com/learn-co-curriculum/kwk-l1-messy_macarena_lab_ruby) -->
+ [User Input Mini Lab]<!-- (https://www.github.com/learn-co-curriculum/kwk-l1-user-input-mini-lab) -->
+ [Met Gala Invitation]<!-- (https://www.github.com/learn-co-curriculum/kwk-l1-invitation-maker-lab) -->
