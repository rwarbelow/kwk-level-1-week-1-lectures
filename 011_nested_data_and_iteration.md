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

Sometimes, though, information can't be reasonably represented in a single array or hash. Imagine, for example, we wanted to store information about a person in an array. Simply keeping track of their name as a string is insufficient to describe them at any non-superficial level.

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

# to prove that ruby hasn't automatically 'unpacked' all of the values from new_york_boroughs into the places_visited array
puts places_visited[3].class
```

As we see above, if we are to print out the `places_visited`, Ruby logs all of the locations, including those within the nested array assigned to the variable `places_visited`. To see just how powerful this ability is (storing arrays within arrays), let's take this a step further and make an alteration to the `new_york_boroughs` array.

The year is 2023, and the union has grown to 51 states. Staten Island has seceded from the State of New York all together. Being responsible programmers we now need to update our `new_york_boroughs` array:

**NOTE:** following is a great opportunity to ask the students for thoughts on what is going to occur. First, alter the `new_york_boroughs` array by popping off the last element. Log the array in IRB before and after to show that it has changed (Staten Island will no longer be present). Next, query the students for what our `places_visited` array will log when we `puts places_visited`. Ask for them to justify their guesses.

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

**LAB ON NESTED ARRAYS**

Now that we have experience with nested arrays, let's move on to nested hashes and see how their behavior is very similar. 
