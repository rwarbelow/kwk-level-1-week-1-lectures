# Ruby Logic and Conditionals Flow - Full Lecture

## Objective

Students will learn about logic, booleans, and if-statements.

## SWBATS

+ LOGIC - Define true and false values in Ruby
+ LOGIC - Use boolean operators `&&` and `||`
+ CONDITIONALS - Use `if`, `elsif`, and `else` statements to control flow.

## Motivation

Programs are interesting because they can deal with uncertainty and ambiguity. Imagine a program that greets you when it starts. We might want it to say "Good morning!" if the time is between 7am and 11am, and "Good afternoon!" if it's between 11am and 5pm, "Good evening!" between 5pm and 9pm, and "Good night!" at all other times.

To do this, we need to understand two major aspects of programming. Logic and Conditionals, which go together like Beyonce and Dancing.

## Logic - 15 minutes

Logic is the science of what is true and what is false. For example, it is true that 1+1 == 2 and it is false that 1+1 == 3. That's logic in a nutshell.

In ruby, we have the concepts of true and false. Let's open IRB and play with some examples you might remember from math classes.

```ruby
1 < 2 #=> true
```

That's the less than operator, `<`. As long as the number on the left is less than the number on the right, Ruby considers the statement `true`.

Ruby supports all your basic numerical comparisons, like `<`, `>`, `<=` and `>=`. You can also do value comparisons - but there's a gotcha.

```ruby
1 = 1
SyntaxError: (irb):2: syntax error, unexpected '=', expecting end-of-input
1 = 1
```

Hmm...why do you think Ruby doesn't like the idea of comparing 1 to 1 using a single `=`? That's right, the single `=` is for variable assignment and we can't get into the existential conversation about what redefining the value of 1 would mean.

So, value comparisons are done with the DOUBLE EQUAL operator `==`.

```ruby
1 == 1 #> true
```

We also have the `NOT EQUAL` operator `!=`

```ruby
1 != 2 #> true
1 != 1 #> false
```

There's also the negation operator `!`. Put that in front of a truthy expression and it will reverse it.

```ruby
!true #> false
!false #> true
!1 #> false
```

hmm, that `!1` is interesting. Why do you think NOT 1 returns false? What do you think the "truthy" value of `1` is? Does one exist? Does it have a value? Then it's considered true.

In ruby, there are only 2 things that are considered false, the literal word `false` and `nil`. Everything else exists, thereby it is considered "truthy"

```ruby
!0 #> false, which means 0 is true.
!"" #> false, which means empty string, still a string, is true
!!0 #> true
!!"" #> true
```

`!!` is a nice way to cast a truthy value into it's true or false. Why?

### Boolean

Boolean operators are really methods which means that they have return values. What do they return? `true` or `false` of course!

In Ruby there are three main boolean operators:

* `!` ("single-bang") which represents "NOT",
* `&&` ("double-ampersand") which represents "AND", and
* `||` ("double-pipe") which represents "OR".

For an `&&` ("and") to evaluate to `true`, both values of either side of the symbol must evaluate to `true`. For example:

```ruby
true && true #=> true

true && false #=> false
```

For an `||` ("or") to evaluate to `true`, only one value on either side of the symbol must evaluate to `true`. For example:

```ruby
false || true #=> true
```

But wait! Imagine this:

```ruby
x = 1
y = 2

x < y && 0
```

Is that trying to say "True" if x is less than y and x is less than 0? If so, we'd expect false right? x isn't less than 0. But we get back true, why? Because Ruby is literaly. The thing on the right is just the number 0, ruby doesn't carry over the idea of comparing x less than to the right. We'd have to do:

```ruby
x = 1
y = 2

x < y && x < 0 #> false
```

**In pairs, work on [Logic Quiz]<!-- (https://github.com/learn-co-curriculum/kwk-l1-logic-quiz) -->** 10 Minutes

Review Quiz - 5-10 minutes.

**TAKE A BREAK - STRETCH / DANCE IN PLACE**

## Conditionals - 10 minutes

The reason why logic is interesting is because it let's us change the flow of our program. What's flow? It's the actual lines of code that get executed.

_You can mention Bret Victor's [Learnable Programming](http://worrydream.com/LearnableProgramming/) and also Bret Victor invented "the swipe" - or what's known as direct pervasive manipulation interfaces - gestures that do things - while at [Apple](http://worrydream.com/#!/Apple)_

Let's pseudocode or example about a greeting based on what time of day it is from earlier (explain what Pseudocode is)

```
if the time is between 7am and 11am
  say Good morning
otherwise, if the time is between 11am - 5pm
  say Good afternoon
otherwise, if the time is between 5pm and 10pm
  say Good evening
otherwise
  say Good night
```

Only one of those branches of logic will execute, depending on the time of day. That's flow control.

To implement that, we need to learn about conditionals, also known as if statements. First, ruby has a magical `Time` function, `Time.now.hour`

```ruby
if Time.now.hour >= 7 && Time.now.hour <= 11
  puts "Good morning!"
elsif Time.now.hour >= 11 && Time.now.hour <= 17
  puts "Good afternoon!"
elsif Time.now.hour >= 17 && Time.now.hour <= 20
  puts "Good evening!"
else
  puts "Good night!"
end
```

Break that down for students, covering `if`, `elsif`, and `else`

### Lab Options - 20-30 minutes.

1. Introduce the `%` modulor or remainder functionality and have them try to solve [Fizzbuzz Lab]<!-- (https://github.com/learn-co-curriculum/kwk-l1-fizzbuzz) --> - This lab is good because it shows the order of the statements mattering and it's a classic interview question and you can say lots of programmers can't solve it :-)

2. [Curfew Checker]<!-- (https://github.com/learn-co-curriculum/kwk-l1-curfew-checker) -->

<!-- 3. [Conditional Diet](https://github.com/learn-co-curriculum/kwk-l1-conditional-diet-lab) - I don't like this lab as diets suck.
 -->
