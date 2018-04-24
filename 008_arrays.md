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
student_one = 'Nancy Sinatra'
student_two = 'David Byrne'
student_three = 'Kate Bush'
# etc...
```

Pretty soon, our system would get out of hand and we would be creating unnecessary work for ourselves by putting the burden on _us_ to remember all of our variables floating around in our program. What we really want is some single variable that holds a collection of our student names.

Lucky for us, arrays do just this in the case of our student names collection:

## Arrays

If we want to hold an **arbitrary amount of something** arrays are just what we want to use. Put simply, an array is a **collection of data** stored all in one place. Arrays are perhaps the most used data structure (which is a fancy term for a 'specific way of storing and accessing data') by programmers.

Let's look at how an array trivializes our initial problem of having too many free floating variables assigned to student names.

#### Creating an array

Just like other types of data in Ruby, (such as a "string", or integer), arrays can be assigned to variable names. If we wanted to create a new blank array, we could do so as follows:

```Ruby
student_names = []
```

This instantiates an empty array that is ready to do all the things an array can, i.e.: have elements added, removed, accessed, looped over, etc. If we wanted to make an array with data in it, we could do the following:

```Ruby
student_names = ['Nancy Sinatra', 'David Byrne', 'Kate Bush']
```

Alright, we have our names stored in this array. Just like with a variable, we can `puts` an array in Ruby, which (being a very friendly programming language), intelligently prints out all of the elements line by line:

```ruby
puts student_names
> Nancy Sinatra
> David Byrne
> Kate Bush
 => nil # if you are wondering why we see the nil, its because that's the return value of the method `puts` itself. IRB prints return values to the terminal by default
```

Excellent! We are off to a running start with arrays. What if we wanted to only access a single element of an array, though? For example, let's say we only wanted to print the first student in the array. Well, arrays have the ability to do just that:

#### Accessing Elements in an Array

```ruby
puts student_names[0]
> Nancy Sinatra
```

This is called **accessing by index**, which provides us a way to get a specific element out of an array. If we wanted to get the second element in the array, we would use `[1]` instead of `[0]`. In programming, arrays (almost) always start with index `0` and increment from there. Saying "the first element" and "the element at index zero" are synonymous.

In addition to accessing by index, Ruby arrays have a battery of methods that make it easy to do common operations such as accessing elements, i.e.: `first` (which returns the first element/element at index 0) and `last` (which returns the last element).

**Query/softball the group in preparation for the mini lab:** in our example, what would `first` and `last` look like if we were to access them by index? (`student_names[0]` && `student_names[2]`)

**SIMPLE LAB/CODEALONG ABOUT ACCESSING DATA IN ARRAY**

#### Growing an Array

Accessing data in an array is only half the story, though! We also want to be able to grow an array by adding data, as well as shrink it. This is trivial for arrays, as they were designed to do just that:

```ruby
student_names.push("Kelsey Lu")
puts student_names
> Nancy Sinatra
> David Byrne
> Kate Bush
> Kelsey Lu
```

As we see above, the array `push` method takes in an argument (or many via: `push('Beatrice', 'Badger', 'Biff')` and appends them to the end of the array.

#### Editing Elements

In addition to adding elements, we can also edit them. For example:

```Ruby
student_names[1] = "Wendy Rene"
```

**Query**: what will the array `puts` now?

**EXPLAIN WRITING DATA TO AN INDEX IN AN ARRAY**

**SHOULD HAVE A SIMPLE LAB/CODEALONG ABOUT WRITING DATA TO AN ARRAY, LIKE A SPOT CORRECTION IN COLORS OF THE RAINBOW**

**EXPLAIN PUSHING TO AN ARRAY**

https://github.com/learn-co-curriculum/kwk-l1-manipulating-arrays-mini-lab

**EXPLAIN THE SIZE OF AN ARRAY**

**EXPLAIN USING A WHILE LOOP TO GO THROUGH ALL ELEMENTS OF AN ARRAY**

**LABS BELOW CAN BE WRITTEN USING WHILE LOOPS WHEN ITERATION IS NEEDED**

https://github.com/learn-co-curriculum/kwk-pattern-lab
https://github.com/learn-co-curriculum/kwk-l1-array-iteration-mini-lab
https://github.com/learn-co-curriculum/kwk-l1-elective-arrays-lab
https://github.com/learn-co-curriculum/kwk-youtube-arrays

**THIS LECTURE SHOULD CREATE THE ANTICIPATION FOR ITERATION with `each`**
