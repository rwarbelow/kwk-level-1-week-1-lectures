**NOTE:** This lecture is relatively short, with the majority of time being allocated for students to go through the lab material in groups/pairs.


# Nested Iteration - Arrays and Hashes

## Objectives

Students will learn about nested iteration, starting with arrays and moving on to hashes.

## SWBATS

+ ARRAYS - access nested arrays
+ HASHES - access nested hashes
+ ARRAYS + HASHES - mix and match nested data structures

## The problem -- shallow data structures

So far, we have been using data structures to represent collections of information and do meaningful things with them, i.e. print out the information of a user's online shopping cart.

Sometimes, though, information can't be reasonably represented in a single array or hash. Imagine, for example, we wanted to store information about a person in an array. Simply keeping track of their name as a string is insufficient to describe their interests, history, friends, etc.

While it is true that, as a general programming heuristic, it's a good idea to follow Einstein's advice when programming:

  _"Everything should be made as simple as possible, but not simpler."_

...sometimes we need a more robust way in which to store data.

## The solution -- Introducing Nested Structures

In addition to storing single values (strings, numbers, etc.) arrays can also store other arrays themselves. Consider the following:

**NOTE: feel free to alter and replace the below with values more local to your students!**

```Ruby
new_york_boroughs = ["Manhattan", "Brooklyn", "Queens", "Bronx", "Staten Island"]
places_visited = ["Italy", "India", "Brazil"]

places_visited << new_york_boroughs

puts places_visited
> Italy
> India
> Brazil
> Manhattan
> Brooklyn
> Queens
> Bronx
> Staten Island

# to prove that ruby hasn't automatically 'unpacked' all of the values from new_york_boroughs into the places_visited array, run the following
puts places_visited[3].class
```

As we see above, if we are to print out the `places_visited`, Ruby logs all of the locations including those within the nested array assigned to the variable `places_visited`. To see just how powerful this behavior is (storing arrays within arrays), let's take this a step further and make an alteration to the `new_york_boroughs` array.

The year is 2023, and the union has grown to 51 states. Staten Island has seceded from the State of New York all together. Being responsible programmers, we now need to update our `new_york_boroughs` array and remove the "Staten Island" element:

---

**INSTRUCTOR NOTE:** following is a great opportunity to ask the students for thoughts on what is going to occur. First, alter the `new_york_boroughs` array by popping off the last element. Log the array in IRB before and after to show that it has changed (Staten Island will no longer be present). Next, query the students for what our `places_visited` array will log when we `puts places_visited`. Ask for them to justify their guesses.

What this exercise demonstrates is one of the trickiest things for beginners to grasp -- multiple variables assigned to the same array reference the _same array in the programs memory_. Up until now, students have only been working with variables that make copies of the values they are assigned to, i.e.:

```ruby
x = 3
y = x
x += 1
x == y # false

# ...not the same as...

x = [1, 2, 3]
y = x
x << 4
x == y # true
```

Do your best to drive this point home without getting into the verbiage of 'pass by reference/pass by value/types' or any other terminology they don't need to get caught up on right now. We want to keep them moving towards doing more with arrays and hashes instead of worrying about rules of computation.

---

```ruby
puts new_york_boroughs
> Manhattan
> Brooklyn
> Queens
> Bronx
> Staten Island

new_york_boroughs.pop # removes the last element from an array and returns it

puts new_york_boroughs
> Manhattan
> Brooklyn
> Queens
> Bronx

puts places_visited
> Italy
> India
> Brazil
> Manhattan
> Brooklyn
> Queens
> Bronx
```

Woah! There is an important change that took place. After removing the last element ("Staten Island") from the `new_york_boroughs` array, it also updated in the `places_visited` array. **Emphasize the following** the array of boroughs in `places_visited` was the **exact same array** assigned to the `new_york_boroughs` array. If we change it anywhere, it is going to change everywhere it is used!

#### Accessing nested arrays

If we wanted to access a nested array, we can do so intuitively:

```ruby
outer_array = ['Foo', 'Bar', ['Hello', 'World'], '!']
inner_array = [2]

puts inner_array[0]
puts inner_array[1]
puts outer_array[3]

# ...alternatively, without using the 'inner_array' variable...
puts outer_array[2][0]
puts outer_array[2][1]
puts outer_array[3]
```

If the second syntax looks a little wonky to you, that's understandable. Let's take a closer look to understand how the computer is interpreting the line `outer_array[2][0]`. First, the computer returns the value from index two (which we know is the `['Hello', 'World']` array). Once it has that, it looks up whatever value is at index 1 in that array and returns it!

**LAB ON NESTED ARRAYS**

Now that we have experience with nested arrays, let's move on to nested hashes and see how their behavior is very similar

## Nested Hashes

Hashes are natural fits for storing data than can be associated with a single unique value (a.k.a. the `key`). Let's assume we are the programmer in charge of the U.S. top secret spy databse. As we know, spies are complex, and thus need a complex data structure to represent them:

```Ruby
spy = {
  "real_name" => "Beatrice Kiddo",
  "alias" => "Ada Lovelace",
  "Languages" => {
    "French" => "Un peu",
    "English" => "Fluent",
    "German" => "Ein bissle"
  }
}
```





# placeholder
