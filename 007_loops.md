# Ruby Loops - Full Lecture

## Objective

Students will learn about loop, break, while, and until

## SWBATS

+ LOOPS - Use `loop` and `break`
+ LOOPS - Use `while` and `until`

## Loops

Remember way back when we learned about methods? We said that there's an issue about repeating a method like a dance over and over and over again.

```ruby
def two_step
  puts "Step to the left..."
  puts "Step to the right."
end

two_step
two_step
two_step
```

How would we tell the `two_step` to just keep on going, to never stop, just keep on repeating? _Do the dance, it never stops_

You'd really want to keep on dancing as long as the music is playing (and if you're me, even after).

## Introducing Loops

**note:** upcoming are a series of code snippets. Each one grows on the previous. Regardless, make sure to describe each line whenever a new concept/keyword/snippet is introduced. A good technique here can be to take turns with the students, where each student reads one line and describes only what that one line does, before moving on to the next students. The first time they will be slow, but after getting the hang of it they will be able to do it rapid fire because they only need to focus on what their single line does, ignoring the larger context.

First things first: the `loop` method. Loop runs the code inside of its block without end. It executes the block top down then repeats, simple as that. If we had backup dancers, and needed to communicate to them what they should do for the whole set, we wouldn't say "step left, step right, step left, step right..." as many times as required. Instead, we would say "Step left, step right. Repeat without end.":

```ruby
loop do
  puts "One..."
  puts "  and two..."
  puts ""
end
```

Try running this in irb. You will notice that your terminal locks up and endlessly processes the same loop, just as we would expect. `ctrl + c` to terminate and type `exit`, or close the tab `cmd + w`. The Ruby program never moves beyond the loop. We can prove this: run the following in irb. `exit` would terminate the irb session if it was ever hit:

```ruby
loop do
  puts "One..."
  puts "  and two..."
  puts ""
end

puts "I'm tired"
exit
```

We never saw our dancer's say "I'm tired". This makes sense, because we never opened up an opportunity to do so. Whenever they were finished with their current move, they were immediately focused on doing their next move, which was to repeat their "one...and two..." move.

[Two Step and Repeat](#) **THIS LAB NEEDS TO BE CREATED**

Of course, sometimes we want to do something many times, but not forever. Eventually, we may want the normal execution of our program to take back over. Let's look at some ways to introduce conditional ending of our loops next.

## `break`

Ruby's `break` statement allows us to end a loop immediately. At whatever point `break` is encountered, the fun stops and Ruby resumes execution outside of the loop. Demonstrate this in irb:

```ruby
loop do
  puts "One..."
  puts "  and two..."
  puts ""
  break
end

puts "I'm tired"
```

Query the students: "If we were to move the `break` to between the two `puts`, how would this change behavior?" Demonstrate this in irb.

Most of the time, we want loops to occur based on certain conditions in programming (just like in dancing). This brings us to our first way of using logic in our loop -- breaking on a conditional. (We have wrapped the following in a method because it displays more logically when run in IRB). After walking them through it line by line, ask your students to guess what this is going to print before running it:

```ruby
def dance
  music_playing = true

  loop do
    if music_playing == false
      break
    end

    puts "One..."
    puts "  and two..."
    puts ""

    music_playing = false
  end

  puts "Everybody freeze!"
end

dance
```

As we currently have it, our loop isn't doing much looping at all. We execute the three `puts` statements, then Ruby reads the `break` statement, and never loops again. A more practical use would be to have our loop repeat a finite number of times. We can do this using a counter, which keeps track of how many times our loop has run:

```ruby
def dance
  moves_completed = 0

  loop do
    if moves_completed == 10
      break
    end

    puts "One..."
    puts "  and two..."
    puts ""

    moves_completed = moves_completed + 1
    puts "#{moves_completed} move(s) completed!"
    # a.k.a. moves_complete += 1
  end

  puts "Everybody freeze!"
end

dance
```

Notice that, in the loop block, we made sure to increment the counter every time the loop runs. At the beginning of the loop, we check the value of that counter and `break` if it has already completed the appropriate amount of times.

What we did in the last few examples is such a commonly expressed way to manage looping (e.g. "do this forever until some condition says stop") that most languages have a specific keyword built in to do just that: the `while` loop.

## `while` Loops

Just as the name implies, the `while` keyword executes a loop 'while' some conditional evaluates to `true`. Let's rewrite the above code block without using `break`:

```ruby
def dance
  moves_completed = 0

  while moves_completed < 10
    puts "One..."
    puts "  and two..."
    puts ""

    moves_completed = moves_completed + 1
    puts "#{moves_completed} move(s) completed!"
  end

  puts "Everybody freeze!"
end

dance
```

Demonstrate the `while` and the `break` with conditional side by side. Query: "What's the difference? Understanding that they do the same thing, is one preferable? Why or why not?

[While Music Playing Lab](#) **THIS LAB NEEDS TO BE CREATED**

You will notice that, with a `while` loop, we are repeating the loop as long as some conditional is `true` or "truthy". In programming, it is also common to need loops that express the following: "until some condition is met, keep repeating this." In fact, this is such a common expression that Ruby gave it a keyword just like `while`! Introducing, `until`:


## `until` Loops

"Until some condition is met, do this thing...". Now is a good time to ask the students to come up with what the code using `until` should look like.

```ruby
# Make note: our variable is now keeping track of the beats left in the song
def dance
  beats_left_in_song = 60

  until beats_left_in_song == 0 do
    puts "One..."
    puts "  and two..."
    puts ""

    beats_left_in_song -= 1
  end

  puts "The song has no more beats we can dance to!"
end

dance
```

Let's tie this back together to our `break` example. You will notice that even with the multiple examples and new keywords above, we have **done nothing new** since our initial use of `break`. We are still asking a simple question: "is some condition true/false? if so, continue/stop." To express the `until` example with `break`:

```ruby
music_stopped = false

loop do
  puts "One..."
  puts "  and two..."
  puts ""
  if music_stopped
    break
  end
end
puts "I never print because the party never ends!"
```

Tying it all together:

[Until the Music Stops Lab](#) **THIS LAB NEEDS TO BE CREATED**

[Command Lines and Menu Lab](#) **THIS LAB NEEDS TO BE CREATED**
