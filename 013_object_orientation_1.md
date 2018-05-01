# Object Oriented Programming Part I - Classes and Instances

**Note:** This section features a large code-along + lab linked at the end of this lecture document. The lecture portion of this should be a high-level overview, following which students should spend a large amount of time working through the provided material. The important point here is to tunnel vision in on what a class and what an instance are in a general sense

## Objectives

Students will learn about the basics of object-oriented programming. This lesson will focus on highlighting the basics of both classes and instances, as well as distinguishing them.

## SWBATS

+ RUBY/OOP - Identify the OOP paradigm
+ CLASS - Create a class
+ INSTANCE - Instantiate an instance

## Introduction - What is Object Orientated Program

Object Oriented Programming, (OOP), is a paradigm that enables programmers to organize their code in easy-to-reason and structured ways. From a zoomed out perspective, object-oriented programming centers around wrapping properties, behaviors, and similar data within pre-defined structures. 

When designing applications, adhering to OOP principles help programmers reason about their code and keep logical parts of the program together. Let's see how these principles can help us structure a basic program that we will use to study the periodic table of elements.

As we work through the architecture of the program, we will see how OOP solves several problems and makes design decisions for us.

## Getting Started

The first thing we want to do is be able to make elements and store references to them. This could be easy enough using a hash:

```ruby
hydrogen = { 
  :name => 'Hydrogen',
  :atomic_number => 1
}
```

While this is appropriate for a single element, it would be inconvenient to make one for every element of the periodic table! Because we know there are two properties we care about, and every single element should have them, (name & atomic number), it would be redundant to write it out 118 times for every element! In addition to being tedious, we would have no indicator of _what_ these objects represent. We would either have to remember, or look at their contents to recognize that they represent elements.

What we really want is something like a 'template' of our element hash above, but without the specific values of name and atomic number filled in. Luckily, OOP has a solution for this specifically: a `class`. 

## What is a Class

Our basic program will have a `class` that we will name `Element` (note the capital 'E'!), which will act as the base data structure that holds all of our elements.

```ruby
class Element
  
  def initialize(name, atomic_number)
    @name = name
    @atomic_number = atomic_number
  end
  
  def name
    @name
  end
  
  def atomic_number
    @atomic_number
  end
  
end
```

It is helpful to think of a `class` as a template. This template describes what information should be filled in when a copy is made. The `@` symbol is saying: "I am an attribute that every copy made from me will have." It is like a field in a form waiting to be completed.

Now that we have this template in place, we will be able to create specific `element`s (note the lower case 'e'!) using it as a guiding structure:

```ruby
hydrogen = Element.new("Hydrogen", 1)
# => #<Element:0x00007fbbec12cfc8 @name="Hydrogen", @atomic_number=1, @phase="gas", @symbol="H"> 
```

We just created an **instance** by calling `Element`'s `new` method! This activated the `initialize` method we defined in our `Element` class, which filled in the template and returned to us the fleshed out hydrogen element.

## What is an Instance

An instance is a 'filled out' copy of the structure a class defines. In our example, we told our program that we wanted the structure of an element, with specific values for hydrogen filled in. Now, we can access those values by calling the **getters** that we defined in the class:

```ruby
hydrogen.atomic_number
# => 1

hydrogen.name
# => "Hydrogen"

# Note: if those methods weren't defined in our class above, Ruby wouldn't know what we wanted returned when we called `hydrogen.name`. The methods are called `getters` in this case because they simply `get` and return the value that is associated with the instance
```

## Instances to the rescue!

Now, instead of having a bunch of hashes representing elements floating around our program, we have a designated Ruby class that describes what these elements should look like, and what they are:

```ruby
periodic_table = []
hydrogen = Element.new("Hydrogen", 1)
helium = Element.new("Helium", 2)
lithium = Element.new("Lithium", 3)

periodic_table.push(hydrogen, helium, lithium)
periodic_table
# => [
    #<Element:0x00007fbbec1b87a8 @name="Hydrogen", @atomic_number=1>, 
    #<Element:0x00007fbbec8a12b8 @name="Helium", @atomic_number=2>,
    #<Element:0x00007fbbec8968b8 @name="Lithium", @atomic_number=3>
# ] 
```

**QUERY THE STUDENTS:** Ok: we know that we can access an instance's `.name` attribute via `instance.name`. Furthermore, we know that `periodic_table` is an array, and we can iterate over arrays using the `.each` method. Understanding this, how could we print out all of the element's names?

## Lab Work

The upcoming labs are going to cover concepts we introduced here in more detail. Make sure you allocate time for students to work on them.

## Moving Forward

In the next lecture, we will build on this periodic table example and look at how classes, in addition to acting as mini instance-producing-factories, encapsulate functionality and behavior. 
