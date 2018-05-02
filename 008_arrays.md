# Ruby Arrays - Full Lecture

## Objectives

Students will learn about creating and manipulating arrays.

## SWBATS

+ ARRAYS - Create
+ ARRAYS - Access by index
+ ARRAYS - Populate
+ ARRAYS - Edit by index
+ ARRAYS - Use size method
+ ARRAYS - Iterate over using index

## Limitations of Variables

Variables are a great way to store data, but they are deficient if we need to store any non-trivial amount of data. Imagine we are making a program that keeps track of all of our peer students. It wouldn't be practical to have a variable for every individual student, à la:

```ruby
student_one = 'Cardi B'
student_two = 'Beyonce'
student_three = 'Adele'
# etc...
```

**Note:** Feel free to swap these names out with whoever you like or other people that your students will associate with. Make sure to do a "find and replace all" if you are changing them!

This solution is sub-optimal. Imagine that we had a new student in our class and needed to add them to our program. As this currently stands, we would have to create a new variable and update the source code itself: `new_student = Ariana Grande`.

Pretty soon, our system would get out of hand and we would be creating unnecessary work for ourselves by putting the burden on _us_ to remember all of our variables floating around in our program. What we really want is some single variable that holds a collection of our student names.

Lucky for us, arrays do just this in the case of our student names collection:

## Arrays

If we want to hold an **arbitrary amount of something** arrays are just what we want to use. Put simply, an array is a **collection of data** stored all in one place. Arrays are perhaps the most used data structure (which is a fancy term for a 'specific way of storing and accessing data') by programmers. Arrays can be used to hold groups of similar data, such as a record of payments, city names, or items in the 'cart' of a website.  

Let's look at how an array trivializes our initial problem of having too many free floating variables assigned to student names.

#### Creating an array

Just like other types of data in Ruby, (such as a "string", or integer), arrays can be assigned to variable names. If we wanted to create a new blank array, we could do so as follows:

```Ruby
student_names = []
```

This creates an empty array just like `""` created an empty string. Our `student_names` array is now ready to do all the things an array can, i.e.: have elements added, removed, accessed, looped over, etc. If we wanted to make an array with data in it (such as several strings), we could do the following:

```Ruby
student_names = ['Cardi B', 'Beyonce', 'Adele']
```

Alright, we have our names stored in this array. Just like with a variable, we can `puts` an array in Ruby, which (being a very friendly programming language), intelligently prints out all of the elements line by line:

```ruby
puts student_names
# > Cardi B
# > Beyonce
# > Adele
# > => nil # if you are wondering why we see the nil, its because that's the return value of the method `puts` itself. IRB prints return values to the terminal by default.
```

Excellent! We are off to a running start with arrays. What if we wanted to only access a single element of an array, though? For example, let's say we only wanted to print the first student in the array. Well, arrays have the ability to do just that:

#### Accessing Elements in an Array

```ruby
student_names[0]
# => "Cardi B"
```

This is called **accessing by index**, which provides us a way to get a specific element out of an array. If we wanted to get the second element in the array, we would use `[1]` instead of `[0]`. In programming, arrays (almost) always start with index `0` and increment from there. Saying "the first element" and "the element at index zero" are synonymous.

In addition to accessing by index, Ruby arrays have a battery of methods that make it easy to do common operations such as accessing elements, i.e.: `first` (which returns the first element/element at index 0) and `last` (which returns the last element).

**Query/softball the group in preparation for the mini lab:** in our example, what would `first` and `last` look like if we were to access them by index? (`student_names[0]` && `student_names[2]`)

**SIMPLE LAB/CODEALONG ABOUT ACCESSING DATA IN ARRAY USE FIRST/LAST AND ACCESS BY INDEX**

#### Growing an Array

Accessing data in an array is only half the story, though! We also want to be able to grow an array by adding data, as well as shrink it. This is trivial for arrays, as they were designed to do just that:

```ruby
student_names.push("Rihanna")
puts student_names
# > Cardi B
# > Beyonce
# > Adele
# > Rihanna
#  => nil
```

As we see above, the array `push` method takes in an argument (or many via: `push('Beatrice', 'Badger', 'Biff')` and appends them to the end of the array. We can also use the shorthand syntax for `push`, by 'shoveling' into the array:

```Ruby
student_names << "Lady Gaga"
puts student_names
# > Cardi B
# > Beyonce
# > Adele
# > Rihanna
# > Lady Gaga
#  => nil
```

#### Editing Elements

In addition to adding elements, we can also edit them. Remember how we could `puts` a single element in an array via `puts student_names[0]`? If we think about it for a moment, we can see that all that's really happening is:
  - The computer is retrieving the first element from the array
  - That element is then handed over to the `puts` method, which prints it
  - `student_names` has no knowledge of `puts`, and `puts` has no knowledge of `student_names`; they are both doing their single task!
If we can retrieve these elements from the array, it follows that we can also edit them!

```Ruby
student_names[1] = "Katy Perry"
```

Just like we described with `puts` taking the result of `array[index]`, we are assigning the value of "Katy Perry" to the index.

**Query**: what will the array `puts` after we execute the above code snippet?

**SHOULD HAVE A SIMPLE LAB/CODEALONG ABOUT EDITING/PUSHING DATA TO AN ARRAY, LIKE A SPOT CORRECTION IN COLORS OF THE RAINBOW**

<!-- https://github.com/learn-co-curriculum/kwk-l1-manipulating-arrays-mini-lab -->

#### Getting and Using the Size

There are many reasons we may want to determine the size, or how many elements, an array has. As one example, imagine we wanted an immediate answer on how many classmates we have. Instead of going through the array, counting one by one, we could simply call the `arr.size` method:

```Ruby
student_names.size
# => 5
```

The `size` method has a use well beyond just telling us how many elements are in an array. It can also be used as a "stop here!" value when 'looping' or 'iterating' over the elements in the array. We could go through the array, index by index, until we get to an index that is equal to the `size` of the array.

Remember: indexes start at 0 so _an array won't have an index the same value as its `.size`!_

Consider the following:

```Ruby
current_idx = 0
while current_idx < student_names.size
  current_student = student_names[current_idx]
  puts "#{current_idx}: #{current_student}"
  current_idx += 1
end

# > 0: Cardi B
# > 1: Kate Perry
# > 2: Adele
# > 3: Rihanna
# > 4: Lady Gaga
#  => nil
```

**Query:**
  - "If we didn't have our `current_idx += 1` in the loop, what could we expect would print out?"
  - Reinforce that we iterate until `index == arr.size - 1`: "How could we re-write this with an `until` statement?"

Here, we see the beginnings of how we can meaningfully use all of the elements in an array. What we just did in the example above was:
  - Access an element in the array
  - Do something (in our case, print) the element with some additional information (the index)
  - Move on to the next element, unless finished

Going forward, we will look at even more convenient ways to do this common pattern of doing something with every element of an array.

<!-- https://github.com/learn-co-curriculum/kwk-l1-array-pattern-lab -->

<!-- https://github.com/learn-co-curriculum/kwk-l1-array-iteration-mini-lab -->

<!-- https://github.com/learn-co-curriculum/kwk-l1-elective-arrays-lab -->

<!-- https://github.com/learn-co-curriculum/kwk-youtube-arrays -->
