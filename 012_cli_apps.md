# Nested Iteration - Arrays and Hashes

## Objectives

Students will learn about making their code interactive via the command line.

## SWBATS

+ RUBY/CLI - use the GETS method
+ RUBY/CLI - use data from GETS
+ RUBY/CLI - print to the CLI
+ RUBY - architect a basic looping program structure


## The CLI

The CLI, or Command Line Interface, is the 'bread and butter' way programmers interact with computers. While it may seem intimidating at first, the CLI will only become more and more convenient, easy to read, and friendly as your programming skills improve.

Consider this: we may initially see the CLI as this complex alternative way of interacting with computers, (as opposed to using windows, icons, clicking on drop-down menus, etc.). The reality is, all of those features are built _on top of_ the core functionality the CLI provides you with. It may seem strange now, but it's likely that, down the road, you will find the graphical user interface of windows/menus/clicking as the complex alternative to the CLI!

## The CLI as a Portal to our Programs

In addition to enabling us general access to the computer, the CLI can be used as a way to interact with live running programs that we have made ourselves. In this lecture and subsequent labs, we are going to work on getting information from the CLI into our Ruby code and printing information back out. We will be making our first 'living and running' program!

## Capturing Input from the CLI

If you have been working in IRB at all, or `puts`'ing out results from code you ran, you have already been utilizing the CLI in your Ruby code. We know that printing to the CLI is trivial:
```ruby
puts "Beyoncé had one of the best videos of all time!"
```

As it turns out, retrieving information from the CLI is just as trivial:

```ruby
apology = gets # the opposite of `puts`

# here, the CLI will wait for input and, once the user hits enter, whatever was typed will be assigned to the variable `apology`

# If we were to type: I'm sorry, Taylor [enter]...
# we will see that it has been assigned to our variable
apology
# => "I'm sorry, Taylor\n"
```

You will notice the `\n` at the end of the string. This is an 'escaped character'. The `\` is telling the computer "Heads up! You have a special character next that is supposed to represent something other than its plain value!" In our case, the escaped `n` says to the computer "I am a new line". This means that whenever we print out a string with an escaped `\n`, a new line will be printed at that point in the string. For example:

**QUERY THE STUDENTS**: what will the following print?

```Ruby
puts "Hello\nWorld\n!"
# Hello
# World
# !
#  => nil
```

From here on out, we are going to use `gets.chomp`, which automatically removes the newline character from CLI input. Just as the name implies, `.chomp` "chomps" off the newline that is automatically added.

## Connecting the CLI to Ruby

If we can capture input as a string from the CLI, it follows that we can use it in our Ruby code:

**NOTE:** Do not copy and paste the whole snippet. Run the lines up to the `gets` then provide first "Katniss" followed by "Everdeen" at the next prompt (or whatever name you would like to use!)

```ruby
game_number = "74"

puts "Please input your first name:"
first_name = gets.chomp

puts "Please input your last name:"
last_name = gets.chomp

"Welcome to the #{game_number}th Hunger Games, #{first_name} #{last_name}"
# => "Welcome to the 74th Hunger Games, Katniss Everdeen"
```

## Making an Ongoing Program

Let's take this a step further. So far, we have only made one-off Ruby scripts that take in data, process it, and spit out a result, then promptly die. We want to have lasting creations though! Let's make a program that runs forever and provides some type of service:

**QUERY:** Now is a good time to ask students to ideate a solution to the following prompt: "Make a program that takes in a single integer value, and prints 'odd' or 'even' depending on which it is. The program should run forever, always waiting for input after it processes the previous". This has a few gotchas. Help them along the way by reminding them of the `loop do` construct. Expect the initial solution to not account for the input coming in as a string. Before giving them the answer, make sure to show that it's not working correctly unless converted to an integer. Finally, this is a good time to introduce the modulo (`%`) operator. If they are having trouble ideating how to check whether a value is odd or even, help empower them by asking if anyone can google "How to check if a number is odd/even in ruby?".

```ruby
loop do
  input = gets.chomp
  input = input.to_i # the input comes in as a string. this converts it to an integer

  if input % 2 == 0
    puts "even!"
  else
    puts "odd!"
  end
end
```

## My First CLI App

Coming up, we will work on a lab in which we make a basic calculator application. To get the students off on the right foot, show them the following example of how a CLI app can route input to different methods:

```ruby
def plus_one(int)
  int + 1
end

def minus_one(int)
  int - 1
end

loop do
  input = gets.chomp
  input_array = input.split(" ") # makes an array of the string values, using space as a delimiter
  # i.e. if input is "3 ++" we will receive ["3", "++"]

  number = input_array[0].to_i
  operator = input_array[1]

  if operator == "++"
    puts plus_one(number)
  elsif operator == "--"
    puts minus_one(number)
  else
    puts "I don't know how to do that! The input should be '<number> <[++, --]>'"
  end


end
```
