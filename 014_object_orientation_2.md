# Object Oriented Programming Part II - Methods, Variables, Scoping


## Objectives

The second lesson on object oriented programming will dive deeper into class methods and variables, and further distinguish a Class from the instances it may generate.

## SWBATS

+ RUBY/OOP - Distinguish and implement class vs. instance variables
+ RUBY/OOP - Distinguish and implement class vs. instance methods

## Introduction - Classes as Objects

All objects are bundles of data and logic –– or attributes and behavior. We understand this to be true of instances of a class. For example, when we made Element instances in the previous lecture, we recognized that each individual object encompassed attributes that belonged to it and it alone (atomic number, name, etc.). In addition to attributes, objects own methods as well. 

Let's take this a step further and look at how classes themselves (and not just their instances) can own functionality and attributes as well. We will define our `Element` class again, and add a new class, `Quizzer`, which will manage all of the functionality required to quiz us on facts about the periodic table (flashcard style):

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


class Quizzer

  # @@ means its a CLASS variable! Capital Q Quizzer owns it!
  # remember: unlike instances there, is only one of any given Class, so only one Quizzer.periodic_table
  @@periodic_table = []
  
  # self. before a method means its a CLASS method! Our Quizzer has no `initialize` method, and does not make instances.

  # the Quizzer object is a natural place for us to keep track of all the elements we want to be practicing on.
  def self.add_element
  end
  
  # this will take in a single element instance and quiz the user.
  def self.quiz_element
  end
  
  # this will start our quizzing routine! The main goal of our program!
  def self.start_quiz
  end
  
end
```

While we have already been using the `Element` class as a template for `element` object instances, it's important to recognize that the class itself is also an object. If our definition of an object is a bundle of code that contains attributes and behaviors, then the entire `Quizzer` class itself absolutely qualifies. 

The `Quizzer` class, instead of being responsible for making `quiz` instances, owns the methods that will manage the testing _as well as_ the variable that will hold all of our element instances.

Make note of the `@@` on our class variable and the `self.` before our class methods. These signify that they belong to the class itself (of which there is only one) and _not_ instances of the class.  

## Adding functionality

Let's start building out the functionality we need to quiz ourselves on our periodic table knowledge. First, let's provide the ability to add elements to our periodic table.

**NOTE:** We are making new instances of `elements` in our `.add_element` method. Make sure the `Element` class is in scope/defined if using IRB!

Following, we want to be able to call a method on our `Quizzer` class which will start iterating through the elements and testing us on their atomic numbers:

```ruby
class Quizzer

  @@periodic_table = []
  
  def self.add_element(element)
    @@periodic_table << element
  end
  
  def self.quiz_element(element)
    puts "What is the atomic number of #{element.name}?"
    answer = gets.chomp.to_i # making sure we convert it to an integer
    
    if answer == element.atomic_number
      puts "That's correct!"
    else
      puts "Oops! #{element.name} has an atomic number of #{element.atomic_number}. You provided: #{answer}"
    end
  end
  
  def self.start_quiz
    @@periodic_table.each do |element|
      self.quiz_element(element)
    end
    puts "Quiz Over!"
  end
  
end

Quizzer.add_element(Element.new("Hydrogen", 1))
Quizzer.add_element(Element.new("Helium", 2))
Quizzer.add_element(Element.new("Lithium", 3))

```

**NOTE:** There is a lot of code here, which some students will pick up on immediately and others will struggle with. Now is a great time to _slow the pace down_. Go line by line through the whole `Quizzer` class with the students. Ask them to describe what each filled out class method does, allowing students to be responsible for describing single lines of code before moving on to the next student (a la popcorn reading style). Don't hesitate to ask redundant questions: "Why do these methods have `self.` at the start, but our `Element` methods didn't? How does a `class` method differ from an `instance` method?"

## Improving our Application

Go ahead and run this in IRB (make sure `Element` and `Quizzer` are defined!). The application works pretty well, but you will likely find it easy to beat. Our elements are in ascending order by atomic weight. Split up into pairs/groups and work on delivering the following:

  - Add more elements!
  - Implement a class method, `self.quiz_random_element` which samples a random element from the class `@@periodic_table` variable and then passes it along to the quiz method we already built
  - add in class attributes to keep track of quizzing success record, i.e. an attribute keeping track of total attempts and an attribute keeping track of successful answers count

**Students should now work on the labs/Learn.co material, which reinforces Ruby object oriented programming principles** 

<p data-visibility='hidden'>KWK-L1 Class Variables and Class Methods</p>
