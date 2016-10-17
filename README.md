# `case` Statements

## Objectives:

1. Distinguish a `case` statement from other patterns of flow control.
2. Identify when to use a `case` statement.
3. Write a `case` statement

## What is a `case` Statement?

A case statement is a powerful tool to test for certain conditions. They are used to run multiple conditions against one value. There are three basic steps to creating a case statement. First, we'll need a value. Second, we'll want one or more conditions to compare to the value. Third, we'll add the code we want to run if that condition is met. Let's walk through these steps in more detail below.

### Why Use a `case` Statement?

In the previous lessons, we've learned about using `if`, `elsif`, and `else` statements to enact flow control in our programs. Let's look at an example of using `if` statements that would benefit from being refactored to use a `case` statement instead. 

Let's say we have a program that sets a `name` variable equal to a person's name. Our program needs to execute certain code depending on what that person's name is. 

```ruby
name = "Alice"

if name == "Alice"
  puts "Hello, Alice!"
elsif name == "The White Rabbit"
  puts "Don't be late, White Rabbit"
elsif name == "The Mad Hatter"
  puts "Welcome to the tea party, Mad Hatter"
elsif name == "The Queen of Hearts"
  puts "Please don't chop off my head!"
else
  puts "Whoooo are you?"
end 

```

Above we are using many `if` and `elsif` statements to check if the value of our name variable matches a particular string by using the comparative operator (`==`) in each one. 

**Top-Tip:** *Remember that the assignment operator (*`=`*) is distinct from the comparative operator (*`==`*).*

Using `if` and `elsif` statements in this manner creates "code smell"—a piece of code that is needlessly complex or difficult to read. Not only are we using a lot of `if` statements, but we are being repetitive in our use of the comparative operator (`==`). We can eliminate this "code odor" by refactoring our flow control to use a `case` statement instead. The `case` statement will allow us to run multiple conditions against the same value, meaning that we can check the `name` variable against a variety of conditions without repeating our use of the comparative operator (`==`) in each one. 

Let's take a look: 

```ruby
case name 

  when "Alice"
    puts "Hello, Alice!"
  when "The White Rabbit"
    puts "Don't be late, White Rabbit"
  when "The Mad Hatter"
    puts "Welcome to the tea party, Mad Hatter"
  when "The Queen of Hearts"
    puts "Please don't chop off my head!"
  else 
    puts "Whoooo are you?"
end
```

### Writing a `case` Statement

Now that we understand *when* to use a `case` statement in place of a series of `if` and `elsif` statements, let's look at *how* to build a `case` statement from scratch. 

#### Step 1: Create a Value

A case statement starts with the `case` keyword followed by a value to test.

```ruby
case greeting
# ...
end
```

#### Step 2: Create the Conditions

Next, the `when` keyword is followed by a condition.

```ruby
case greeting
  when "unfriendly_greeting"
    #...
  when "friendly_greeting"
    #...
end
```

#### Step 3: Add the Code

The functionality that we wish to happen when the condition is met is placed on an indented line directly under the `when` line. Let's define the behavior:

```ruby
greeting = "friendly_greeting"

case greeting
  when "unfriendly_greeting"
    puts "What do you want!?"
  when "friendly_greeting"
    puts "Hi! How are you?"
end
```

## Example 1: Weather

In this example, we set the `current_weather` to `"raining"`. Next, we use `when` statements to describe a list of possible matches. Since `current_weather === "raining"` we'd expect this code to put `"grab an umbrella"`.

```ruby
current_weather = "raining"

case current_weather
  when "sunny"
    puts "grab some sunscreen!"
  when "raining"
    puts "grab an umbrella"
  when "snowing"
    puts "bundle up"
end
```

## Example 2: Grades

This example requires a basic understanding of `gets.chomp`. It allows us to get a user's input, and use it in our code. [Read more on what it does here.](http://stackoverflow.com/questions/23193813/how-does-gets-and-gets-chomp-in-ruby-work)

Here, we are prompting the user to input a student's grade. Based on that `grade`, the program then prints out the string associated with the matching condition. If the user enters "A", then `grade = "A"`. Since `grade === "A"`, Ruby will print `Good job, Homestar!` to the screen. 

```ruby
print "Enter your grade: "
grade = gets.chomp

case grade
  when "A"
    puts "Good job, Homestar!"
  when "B"
    puts "You can totally do better!"
  when "C"
    puts "Find a mentor to help you!"
  else
    puts "You're just making that up!"
end
```