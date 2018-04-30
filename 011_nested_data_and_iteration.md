**NOTE:** This lecture should be relatively short, with the majority of time being allocated for students to go through the lab material in groups/pairs.


# Nested Iteration - Arrays and Hashes

## Objectives

Students will learn about nested iteration, starting with arrays and moving on to hashes.

## SWBATS

+ ARRAYS - access nested arrays
+ HASHES - access nested hashes
+ ARRAYS + HASHES - mix and match nested data structures

## The problem -- Shallow Data Structures

So far, we have been using data structures to represent collections of information and do meaningful things with them, i.e. print out the information of a user's online shopping cart.

Sometimes, though, information can't be reasonably represented in a single array or hash. Imagine, for example, we wanted to store information about a person in an array. Simply keeping track of their name as a string is insufficient to describe their interests, history, friends, etc.

While it is true that, as a general programming heuristic, it's a good idea to follow Einstein's advice when programming:

  _"Everything should be made as simple as possible, but not simpler."_

...sometimes we need a more robust way in which to store data.

## The solution -- Introducing Nested Structures

In addition to storing single values (strings, numbers, etc.) arrays can also store other arrays themselves. Consider the following:

**NOTE: feel free to alter and replace the below with values more local to your students!**

```ruby
closet = [
  ["rain jacket", "cardigan", "blazer"],
  ["jeans", "skirt", "capris"],
  ["sneakers", "heels", "flats"]
]

# to prove that ruby hasn't automatically 'unpacked' all of the values from the sub-arrays into the closet array, run the following. Ask them first "what type of variable is closet[0]? (not the value of)"
closet[0].class
# => Array (.class is telling us what type of object it is. try: "hello".class if there is confusion)
```

As we see above, nested arrays have provided a significant amount of organization to our "closet". To see just how powerful this behavior is (storing arrays within arrays), let's take this a step further and keep variables for our different closet sections:

```ruby
tops = ["rain jacket", "cardigan", "blazer"]
bottoms = ["jeans", "skirt", "capris"]
footwear = ["sneakers", "heels", "flats"]

closet = [tops, bottoms, footwear]

# Now imagine we got a new article of clothing. We wouldn't just chuck it into our closet to become a part of a black hole. Instead, we want to update our closet without losing organization:

footwear << "gladiators"

# this has updated the closet, because its the same array:
closet
# => [..., ["sneakers", "heels", "flats", "gladiators"]]
```

---

**INSTRUCTOR NOTE:** What this exercise demonstrates is one of the trickiest things for beginners to grasp -- multiple variables assigned to the same array reference the _same array in the programs memory_. Up until now, students have only been working with variables that make copies of the values they are assigned to, i.e.:

```ruby
x = 3
y = x
x += 1
x == y
# => false

# ...not the same as...

x = [1, 2, 3]
y = x
x << 4
x == y
# => true
```

Do your best to drive this point home without getting into the verbiage of 'pass by reference/pass by value/types' or any other terminology they don't need to get caught up on right now. We want to keep them moving towards doing more with arrays and hashes instead of worrying about rules of computation.

---

#### Accessing Nested Arrays

If we wanted to access a nested array, we can do so intuitively:

**Note:** give them a moment to read this code line by line. Before executing the accesses by index at the bottom of the code snippet below, have it typed out and query the students for what will return.

```ruby
outer_array = ['Foo', 'Bar', ['Hello', 'World'], '!']
inner_array = outer_array[2]
#  => ["Hello", "World"]

"#{inner_array[0]}, #{inner_array[1]}#{outer_array[3]}"
# => "Hello, World!"

# ...alternatively, without using the 'inner_array' variable...
outer_array[2][0] # what do we expect?
# => "Hello"
outer_array[2][1] # what do we expect?
# => "World"
outer_array[3] # what do we expect?
# => "!"
```

If the second syntax looks a little wonky to you, that's understandable. Let's take a closer look to see how the computer is interpreting the line `outer_array[2][0]`. First, the computer returns the value from `outer_array` at index two (which we know is the `['Hello', 'World']` array). Once it has that, it looks up whatever value is at index 1 in that array and returns it. 

Program execution can always be broken down into smaller steps. Practicing identifying the order in which the computer evaluates the written code is worth your time and will speed up your reading comprehension. 


Now that we have experience with nested arrays, let's move on to nested hashes and see how their behavior is very similar.

## Nesting Arrays in Hashes

Hashes are natural fits for storing data that can be associated with a single unique value (a.k.a. the `key`). In addition to being associated with `values` that are strings and numbers, `keys` can point to other data structures (i.e. arrays and hashes).

To understand why this is useful, consider this: if we use the nested array structure above to represent our closet, we have no reasonable way to identify the different parts of our closet. It is as if our closet has several boxes within it that, while they hold similar articles of clothing, have no distinguishing features from the outside describing what their contents are.

Hashes solve this problem by giving us the ability to 'label' said boxes. Let's look at how we can use descriptive `keys` to label our `values`, which are arrays:

**NOTE:** If you initialize the hash with ':' in place of the '=>', the `keys` will automatically converted to symbols (i.e. `"tops"` will become `:tops`)

```ruby
closet = {
  "tops" => ["rain jacket", "cardigan", "blazer"],
  "bottoms" => ["jeans", "skirt", "capris"],
  "footwear" => ["sneakers", "heels", "flats"]
}

closet["tops"]
# => ["rain jacket", "cardigan", "blazer"] 

# furthermore, we can operate on these arrays:

closet["tops"] << "tank top"
closet["tops"]
# => ["rain jacket", "cardigan", "blazer", "tank top"] 
```

**NOTE:** Remind students that `closet["tops"]` first returns the value (array) itself, so its the same thing as doing `["rain jacket", "cardigan", "blazer"] << "tank top"`

## Nesting Hashes

Just like we can nest arrays in hashes, we can nest hashes themselves:

```ruby
closet = {
  "tops" => ["rain jacket", "cardigan", "blazer"],
  "bottoms" => ["jeans", "skirt", "capris"],
  "footwear" => {
    "sport" => ["sneakers", "rock climbing shoes", "cleats"],
    "casual" => ["flats", "boots"],
    "formal" => ["flats", "heels", "pumps"]
  }
}

# We can work with the nested hashes just as you would expect
# What will the following do to the `closet` hash?
closet["footwear"]["misc."] = ["cheetah slippers", "rain boots"]
```

## Putting it All Together

We just explored a very powerful feature: nesting data structures within others. As programmers, we are constantly using structures that enable us to more easily access and work with data. It is important to remember that accessing nested structures can be done step by step, starting at the top-most level and moving downward from there. 

##### [LAB: arrays, nested arrays, patterns][pattern-lab] (make sure you are familiar with this lab and the solution to it. If students get caught up, provide them with the guidance they need to keep moving through the deliverables.)
