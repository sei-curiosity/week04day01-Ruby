[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Introduction to Ruby

![](images/ruby.gif)

## Lesson Objectives
- [Installing Ruby](install-ruby.md)
- [Running your Ruby Scripts](how-to-run-ruby.md)
- Compare/contrast Ruby and Javascript as programming languages
- Identify specific differences between Ruby and Javascript in the following areas...
  - Variables
  - Fundamental Data Types
  - Data Collections
  - Conditionals
  - Data Immutability
- Explain and apply Ranges
- Interact with symbols and explain their significance

## Introduction

Ruby is a server-side language. It was designed and developed in 1995 by [Yukihiro "Matz" Matsumoto](https://en.wikipedia.org/wiki/Yukihiro_Matsumoto) in Japan.

His philosophy in building Ruby was not about simplicity, but making programming in Ruby feel natural in a way that mirrors life.

This brought about a motto that is common among the Ruby community.

> "Matz Is Nice And So We Are Nice"

> "Programmers often feel joy when they can concentrate on the creative side of programming, so Ruby is designed to make programmers happy." — Yukihiro "Matz" Matsumoto

Performing everyday tasks, while intricate and complex, come to you naturally.

> "Ruby is simple in appearance, but is very complex inside, just like our human body." — Yukihiro "Matz" Matsumoto

## Learning a New Language

If you were going to learn a new programming language, what questions would you have? You've already learned one programming language, and you're about to learn another! Think about the things you now know how to do in JavaScript. With this knowledge, consider what you might want to know about Ruby. Take a few minutes to think about some questions that you have about this new language.

Examples:

- How do I define a variable in Ruby? Is it different than in JavaScript?
- Where do I go for information about Ruby? What kind of documentation exists for it?
- Does Ruby have functions?

Ruby and JavaScript each have unique features that you may find useful or ineffective. At the end of the day, you'll find that they share many qualities.


#### Flexibility

Ruby is flexible making it ideal for coding. What this means is that there are no* blackboxes in Ruby. You can open up anything and change it. This could be a powerful tool in the hands of a skilled Rubyist.

#### Readability

Ruby is hyper readable, the lack of `;`, `()`, keywords like `let`, `return`, `function` mean that your semantic naming of methods and variables combined with the semantic nature of the core library methods result in code that feels more like English than a programming language.

![](images/pair.jpg)


```ruby
5.times { print "Hi!" }
```

```ruby
['grookey', 'scorbunny', 'sobble'].each { |pokemon| print pokemon.capitalize  }
```

```ruby
  number = 3
  # => 3

  if( number == 3 ) # with parens
    puts( "It's a 3!" )  
  end  
  # It's a 3!
  # => nil

  if number == 3 # without parens
    puts "It's a 3!"  
  end  
  # It's a 3!
  # => nil
```

## Ruby Basics

### Variables

We no longer need to precede new variables with var. Just use the name of the variable!

* Variables are instantiated as they are used
```rb
name = "Maha"
```
* Written in snake_case. That means all lower case with words separated by underscores.
```rb
first_name = "Salman"
```
* Variable names should still be semantic
* Variables are still assigned using a single equals sign ( = )

```ruby
my_favorite_super_hero = "spoderman"
# => "spoderman"
```

Although we don't use var, there is still syntax to designate whether a variable is local or global.

* Undesignated implies local (e.g., my_number)
```rb
my_number = 10
```
* All-caps implies that your value is constant. Ruby will give you warnings if you try to change the value (e.g., PI = 3.14).
```rb
PI = 3.14
```

### puts

puts (short for "put string") is the equivalent of Javascript's console.log()

```ruby
puts "Hello, Ruby!"
# Hello, Ruby!

```

## Data Types

### Everything Is An Object!

Everything in Ruby is an **object**.
* By "object" we mean that everything has its own set of properties and methods
* Not a new concept. Some data types in Javascript had their own properties and methods (e.g., `string.length`)
* You will learn more about this when you dive into Ruby OOP

### Strings

Words, just like in Javascript.
* Surrounded by single or double-quotes
* Ruby uses similar escape characters
  - [Here is a list of them](http://www.java2s.com/Code/Ruby/String/EscapeCharacterslist.htm)
  - Must instantiate string with double-quotes for escape characters to work

```rb
name = "Peter"
# => "Peter"

full_name = "Peter\nParker"
# => "Peter\Parker"

single_quote = 'Peter\nParker'
# => "Peter\Parker"

puts full_name
# Peter
# Parker
# => nil

puts single_quote
# Peter\Parker
# => nil
```

Not only can you concatenate strings, now you can multiply them too! Remember we couldn't do that in Javascript?

```rb
# Concatenation
"Hey " + "there!"
# => "Hey there!"

# Multiplication
"Hey there! " * 3
# => "Hey there! Hey there! Hey there! "
```

You can concatenate strings but this is NOT recommend.

```ruby
'ryu' + 'ken' # => 'ryuken'
'ryu' + 2 # => TypeError: no implicit conversion of Integer into String
'ryu' + 2.to_s # => 'ryu2'
```

Above we see that we can NOT implicitly convert a non-string into a string (unlike what we have seen in JS).

Use single quotes for strings that are not interpolated.

> Warning: Backticks are not used for strings! They are used to execute commands.

#### String Interpolation 
Interpolation requires double quotes

Sometimes you will want to print out a string that incorporates a variable. For example...

```rb
my_name = "Ahmed"
# => "Ahmed"

puts "Hi my name is: " + my_name
# Hi my name is: Ahmed
# => nil
```

This works fine. Things aren't so simple when that variable is of a different data type. Like a number...

```rb
class_number = 2
# => 2

puts "I am teaching SEI " + class_number
# TypeError: no implicit conversion of Fixnum into String from (pry):26:in `+'
```

In cases like the above, you either need to convert the variable to a string using `.to_s` or use something called "interpolation."

* Surround the non-string variable with a hashtag and curly brackets: `#{variable}`. **If you choose this option, you must use double quotes otherwise the interpolation will not work.**
* No Javascript equivalent [(until ES6 came along)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

```rb
class_number = 9
# => 9

puts "I am teaching SEI #{class_number}"
# I am teaching SEI 9
# => nil
```



### Numbers

Ruby uses same arithmetic operators as Javascript
* `+`, `-`, `*`, `/`, `%`
* Same order of operations too: P.E.M.D.A.S.  

```rb
1 + 2 # Addition
# => 3

6 - 5 # Subtraction
# => 1

5 * 2 # Multiplication
# => 10

30 / 5 # Division
# => 6

31 / 5 # Note: integer division
# => 6

30 % 5 # Modulo (remainder)
# => 0

31 % 5
# => 1

3 ** 2 # Exponentiation
# => 9
```
Examples:

```ruby
p 0.1
p 42
p 124971240712
p 1_234_567
```
Underscores are ignored in Ruby numbers. Making them useful for readability.


### Booleans

Still `true` and `false`.
* We'll be using them in conditionals and comparisons just like in Javascript

Comparison operators in Ruby are nearly identical to Javascript. However, the check for equality is always for both value and data type.
* `<`, `>`, `<=`, `>=`, `==`, `!=`

> Don't worry about `===` in Ruby for now. It [does not](http://mauricio.github.io/2011/05/30/ruby-basics-equality-operators-ruby.html) have the same application as in Javascript.  

Logical operators are also similar.
* `!`, `&&`, `||`

"Truthiness" and "falsiness" are a lot less complicated in Ruby.
* The only falsey values in Ruby are `nil` and `false`

### Nil

Ruby's "nothing".
* The equivalent of Javascript's `null`
* You will usually see it when something does not have a return value (e.g., a `puts` statement)
* Like in Javascript, `nil` is falsey

Need to check if something is `nil`? Use `.nil?`  

> **NOTE:** Any method that ends with a `?` means it will return a boolean value.  

```rb
something = "The Thing"
# => "The Thing"

something.nil?
# => false

something = nil
# => nil

something.nil?
# => true
```

### gets

Ruby also allows us to easily accept inputs from the command line using gets
```ruby
user_input = gets
# => "My input\n" (Note that this line was typed by the user in the terminal)

user_input
# => "My input\n"
```
Some notes about gets...

Usually gets is followed by .chomp, which removes the new line generated by the user hitting return
If you need to convert your value to a number, add .to_i to the end of the method

#### Demo

Let's test gets by using it in a Ruby file...

```ruby
# Run this code in app.rb

# Asks for and stores a command line input into the variable as a string.
puts "How old are you?: "

user_input = gets.chomp.to_i

if user_input > 10
  puts "You are older than ten"
end

# In the terminal from in the same directory as app.rb

$ ruby app.rb
# => How old are you?:
20
# => You are older than ten

$ ruby app.rb
# => How old are you?:
```

### Operators

You’ll use the following list of operators to do math in Ruby or to compare things. Scan over the list, recognize a few. You know, addition + and subtraction - and so on.

```
** !  ~  *  /  %  +  -  &
<< >> |  ^  >  >= <  <= <=>
|| != =~ !~ && += -= == ===
.. ... not and or
```

### Conditionals

Pretty similar to Javascript, with some differences.

- No parentheses or curly brackets required
- Begin blocks using if, elsif (no second "e"!) and else
- We close the whole loop using end
    - This will be used throughout Ruby when dealing with code blocks (e.g., method/function)
...

```ruby
puts "Enter your age "
age = gets.chomp.to_i

if age < 18
  puts "Sorry, You cann't drive."
elsif age >= 18
  puts "Of course, You can drive"
else
  puts "input is invalid"
end
```

#### `if` / `unless`
We also have single-line ifs

```ruby
puts 'you are old!' if age >= 100
```

You may even see `unless`

```ruby
puts 'you are old!' unless age < 100
```
When you see an `unless foo`, read it as `if !foo`

> `if !foo` can always be written as `unless foo` which creates a more readable line


#### Ternary operator  

A ternary operator looks just like we have seen in JS `condition ? true : false`

```ruby
1 > 2 ? "condition is true" : "condition is false"
```

A more real life example is:

```ruby
num.even? ? "#{num} is even!" : "#{num} is odd!"
```

Same as:

```ruby
if num.even?
  "#{num} is even!"
else
  "#{num} is odd!"
end
```
#### Case statement

The case statement in Ruby, can be seen as a shorthand for a series of `if` statements. Unlike other languages, there is no fallthrough. Only the first matching case will be executed.

Example:

```ruby
num_of_wheels = 1

case num_of_wheels
when 1
  p "Unicycle"
when 2
  p "Bicycle"
when 4
  p "Car"
else
  p "I'm not sure"
end
```

##### A More Compact Syntax

There are times when there are a large number of small `when` clauses. Such a case statement easily grows too large to fit on the screen. When this is the case (no pun intended), you can use the `then` keyword to put the body of the `when` clause on the same line.

While this makes for some very dense code, as long as each when clause is very similar, it actually becomes more readable.

When you should use single-line and multi-line when clauses are up to you, it's a matter of style. However, mixing the two is not recommended - a case statement should follow a pattern to be as readable as possible.

Example:

```ruby
person_name = "Salman"

case person_name
when "Ahmed" then p "Lead Instructor"
when "Salman" then p "IA"
else
  p "Student"
end
```

### The Bang Symbol (!)
Exclamation mark

All of the Ruby data types we have discussed so far are mutable.

We can not only change what variables are pointing to in memory, but we can directly modify those values stored in memory as well.
Methods with an ! attached to the end of them usually mean that they will modify the value in memory they are being called on.

```ruby
a = "cheeseburger"
# => "cheeseburger"

a.upcase = "cheeseburger"
# => "CHEESEBURGER"

a
# => "cheeseburger"

a.upcase!
# => "CHEESEBURGER"
```

Things can get tricky when you have multiple variables pointing at the same value. For example...

```ruby
a = "cheeseburger"
# => "cheeseburger"

b = a
# => "cheeseburger"

b.upcase!
# => "CHEESEBURGER"

a
# => "CHEESEBURGER"
```

## Data Type Exercise - Lab (30 minutes) 
Complete the exercises in [this document](data-types-exercises.md
).


## Data Collections

Spend 10 minutes reading through everything up until Hashes.

### Arrays

An ordered collection of related values. Same syntax as Javascript arrays.

- Square brackets
- Values separated by commas
- Zero-indexed

```ruby
numbers = [1, 2, 3]
# => [1, 2, 3]

animals = ["dog", "cat", "horse"]
# => ["dog", "cat", "horse"]

animals[0]
# => "dog"

animals[1] = "elephant"
# => "elephant"

animals
# => ["dog", "elephant", "horse"]
```

Another super cool Ruby feature is that you can perform arithmetic operations on arrays!

```ruby
numbers = [1, 2, 3]
# => [1, 2, 3]

more_numbers = [4, 5, 6]
# => [4, 5, 6]

lots_of_numbers = numbers + more_numbers
# => [1, 2, 3, 4, 5, 6]

lots_of_numbers - [4, 5, 6]
# => [1, 2, 3]

numbers * 3
# => [1, 2, 3, 1, 2, 3, 1, 2, 3]
```

#### Array Methods

Ruby is very nice. It provides us with an extensive library of array methods we can use to traverse and manipulate arrays.

- [The Ruby documentation for `Array` is a great resource for learning more about these methods](http://ruby-doc.org/core-2.6.1/Array.html).
- Can't go over them all, but chances are if you could do it in Javascript then you can do it in Ruby.

**IMPORTANT**: You DO NOT need to memorize these. The following is just a sample of array methods available to you. You'll come to be more familiar with these as you need them and look them up in documentation.

`tl;dr: The more you Google them, the better you'll remember them.`

#### Push/Pop

These Javascript methods also exist in Ruby and are used the same way.

```ruby 
numbers = [1, 2, 3, 4, 5]
# => [1, 2, 3, 4, 5]

numbers.push(6)
# => [1, 2, 3, 4, 5, 6]

numbers.push(7, 8, 9)
# => [1, 2, 3, 4, 5, 6, 7, 8, 9]

numbers.pop
# => 9

numbers
# => [1, 2, 3, 4, 5, 6, 7, 8]
```

#### Sort

Organizes array values from lowest to highest. Numbers and strings.
Compare this to how Javascript handles `sort()`

```ruby
numbers = [3, 1, 5, 2, 4]
# => [3, 1, 5, 2, 4]

numbers.sort
# => [1, 2, 3, 4, 5]
```

#### Delete

- Removes an argument from an array. If there are multiple instances of that argument, it will delete them all
- Look up: .delete_at(), .slice()

```ruby
numbers = [3, 1, 2, 2, 4]
# => [3, 1, 2, 2, 4]

numbers.delete(2)
# => 2

numbers
# => [3, 1, 4]
```

### Symbols

Symbols are immutable, constant values. That means they contain the same value through the entirety of a program and cannot be changed.

- Kind of like a string that never changes
- Syntax: variable_name = :symbol_name
- No Javascript equivalent (until ES6 came along!))

```ruby
favorite_animal = :dog
# => :dog

favorite_animal.upcase!
# NoMethodError: undefined method `upcase!' for :dog:Symbol
# Did you mean?  upcase
```
#### When/why would you use symbols?

* Most common use is as keys in hashes, the Ruby equivalent of objects (more on that later)
* Make sure values that need to be constant stay constant
* Enhance performance, use less memory

Every string you create is unique and takes up space on your computer, even if they're the same value! When we're busy looking up key/value pairs, we don't want to be wasting memory - we want it to be fast!

#### Let's watch:
```ruby 
"Your Name".object_id
#=> a number

"Your Name".object_id
#=> a different number

:your_name.object_id
#=> a number

:your_name.object_id
#=> the same number!
```

### Hashes

A Ruby hash is an unordered, dictionary-like collection organized by key-value pairs.

`A hash is very similar to a Javascript object.`

```ruby
Ahmad = { name: 'Ahmad', age: 0 }
```

Notice that is looks exactly like a JS object except the keys are symbols, not strings.

```ruby
sei_class = {
  teacher: "Ahmad",  
  students: ["Tony", "Steve", "Bruce"],  
  classroom: 3,
  in_session: true,  
  schedule: {  
    morning: "Ruby Basics",
  }
}  
# => {:teacher=>"Ahmad", :students=>["Tony", "Steve", "Bruce"], :classroom=>3, :in_session=>true, :schedule=>{:morning=>"Ruby Basics"}}
```

Accessing hash values...

```ruby
sei_class[:teacher]
# => "Ahmad"
```
Modifying hash values...

```ruby
sei_class[:teacher] = "Maha"
# => "Maha"
```

You can also use strings as hash keys... 

```ruby
sei_class = {
  "teacher" => "Ahmad",  
  "students" => ["Tony", "Steve", "Bruce"],  
  "classroom" => 3,  
  "in_session" => true,  
  "schedule" => {  
    "morning" => "Ruby Basics",
    "afternoon" => "FEWD"
  }
}  
```
Then can access in this way...

```ruby
sei_class["teacher"]
# => "Ahmad"
```

And modify...
```
sei_class["teacher"] = "Maha"
# => "Maha"
```

**Note the use of => (or "hash rockets") instead of : when using strings as keys.**

#### Hash Methods

Like arrays, Ruby also provides us with a library of hash methods.

 * [Again, the Ruby documentation is a great resource](http://ruby-doc.org/core-2.6.1/Hash.html).
 * As mentioned with arrays, do not worry about memorizing these methods. Just know how to look them up should the need arise.

#### Keys

Returns an array with all the keys in a hash.

```ruby
sei_class.keys
# => [:teacher, :students, :classroom, :in_session, :schedule]
```

#### Merge

Combines two hashes. If both of your hashes have the same key, the one in the hash you set as the argument in the parameters will take precedence.

```ruby
classroom = {
 room: 1  
}  
# => {:room=>1}

locations = {
 location_one: "Gotham",  
 location_two: "NY",  
 location_three: "Jeddah"  
}  
# => {:location_one=>"Gotham", :location_two=>"NY", :location_three=>"Jeddah"}

silly_hash = classroom.merge(locations)
# => {:room=>1, :location_one=>"Gotham", :location_two=>"NY", :location_three=>"Jeddah"}

classroom
# => {:room=>1}

locations
# => {:location_one=>"Gotham", :location_two=>"NY", :location_three=>"Jeddah"}

silly_hash
# => {:room=>1, :location_one=>"Gotham", :location_two=>"NY", :location_three=>"Jeddah"}
```

#### Ranges

Use ranges to quickly generate arrays of data types.

Parentheses Min and max value, separated by two periods. Generate array using .to_a method

```ruby
(1..5).to_a
# => [1, 2, 3, 4, 5]

("a".."z").to_a
# => ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]
```

Normally, only two dots are used. If a third dot is used, the last value in the range is excluded.

```(0...5)``` represents the numbers 0 through 4.

## Lab: Data Collection Exercise
Complete the exercises in [this document](data-collections-exercises.md).


## Blocks

Any code surrounded by curly braces is a block.

```ruby
2.times {
  print "Hey!"
}
```

With blocks, you can group a set of instructions together so that they can be passed around your program.

The curly braces can also be traded for the words do and end, which is nice if your block is longer than one line.

```ruby
loop do
  print "Hey!"
end
```

## Loops

One of the most common things we do as developers is to iterate through data structures.

Whenever we talk about data in Ruby, its important to review how Ruby handles groups of data.

We learned how to iterate over collections in Javascript using loops. Now we're going to learn the same in Ruby.

### Review JS Loops

<details>
<summary>What loops did we use in Javascript?</summary>
<code>while</code>, <code>do...while</code>, <code>for</code>, <code>for...in</code>, <code>.forEach</code>
</details>

### Looping with Ruby

In JS if we wanted to print numbers 0 through 3 we would:

```javascript
for(var i = 0; i < 3; i++) {
  console.log(i);
}
// > 0
// > 1
// > 2
```

In Ruby this is much cleaner:

```ruby
3.times { |i| puts i }
# > 0
# > 1
# > 2
```
```
names = ["Ebere","Yassir","Ahmad", "Atheer", "Mike", "Sami" , "Alanoud" ]
names.length.times{ |i| puts "hello #{i} = #{names[i]}"}

```


`times` is a method that takes a _block_.  A block is just a chunk of code that may or may not take arguments.  The closest thing to a block in ES6-land would be an (anonymous) arrow function.

We also have `.upto` and `.downto` methods for looping.

> Yes there _are_ `for` loops in Ruby but we DO NOT use them

But, the closest equivalent to Javascript's `for` loop is Rubys `for...in` loop

```rb
users = ["Blossom", "Bubbles", "Buttercup"]
for user in users do
  puts user
end
```

We can also iterate over arrays:

```ruby
arr = [10, 20, 30]

arr.each { |num| puts num }
# > 10
# > 20
# > 30

arr.map { |num| num / 10 }
# => [1, 2, 3]
```

`each` and `map` also take blocks (just like `forEach` and `map` take callbacks in JS).

### What is the difference between map & each?

Each is like a more primitive version of map…

It gives you every element so you can work with it, but it doesn’t collect the results.
Each always returns the original, unchanged object.
While map does the same thing, but…
It returns a new array with the transformed elements.


For blocks with longer lines or multiple lines, replace `{` and `}` with `do` and `end`

```ruby
arr.map do |num|
  "#{num / 10} is great!"
end
# => ["1 is great!", "2 is great!", "3 is great!"]
```

And we can iterate over hashes:

```ruby
hash = { a: 1, b: 2, c: 3 }
hash.each do |key, val|
  puts "the value of #{key} is #{val}"
end
# > the value of a is 1
# > the value of b is 2
# > the value of c is 3
```

### Exercise: Other types of Loops in Ruby (30 minutes)

#### [while](https://ruby-doc.org/core-2.6.1/doc/syntax/control_expressions_rdoc.html#label-while+Loop)

```rb
input = ""
puts "You must guess the Magic Words to exit the while loop!"
while input != "Magic Words" do
  puts "What are the Magic Words?"
  input = gets.chomp
end
puts "You made it out! Congrats!"
```

#### [until](https://ruby-doc.org/core-2.6.1/doc/syntax/control_expressions_rdoc.html#label-until+Loop)


```rb
input = ""
puts "You must guess the Magic Words to exit the while loop!"
until input == "Magic Words" do
  puts "What are the Magic Words?"
  input = gets.chomp
end
puts "You made it out! Congrats!"
```

#### [loop](https://ruby-doc.org/core-2.6.1/Kernel.html#method-i-loop)

```rb
puts "You must guess the Magic Words to exit the while loop!"
loop do
  puts "What are the Magic Words?"
  input = gets.chomp
  break if input == "Magic Words"
end
puts "You made it out! Congrats!"
```

#### [.times](https://ruby-doc.org/core-2.6.1/Integer.html#method-i-times)

```rb
users = ["Blossom", "Bubbles", "Buttercup"]
users.length.times do |index|
  puts users[index]  
end
```
> [**Further Reading on Ruby loops**](http://www.tutorialspoint.com/ruby/ruby_loops.htm)


### Exercise: Practice Each (15 minutes)

Use `each` to do the following...

- Say hello to everybody in the below array of names (sample output: `Hello Donald!`).

  ```ruby
  names = [ "Donald", "Daisy", "Huey", "Duey", "Luey" ]
  ```

- Print out the squared values of every number in this numbers array.

  ```ruby
  numbers = [ 1, 3, 9, 11, 100 ]
  ```

- Print out the Celsius values for an array containing Fahrenheit values.

  > Hint: `C = (F - 32) * (5 / 9)`

  ```ruby
  fahrenheit_temps = [ -128.6, 0, 32, 140, 212 ]
  ```

- Insert all the values in the `artists` array into the `ninja_turtles` array.

  ```ruby
  artists = [ "Leonardo", "Donatello", "Raphael", "Michelangelo" ]
  ninja_turtles = []
  ```

- **Bonus:** Print out every possible combination of the below ice cream flavors and toppings.

  ```ruby
  flavors = [ "vanilla", "chocolate", "strawberry", "butter pecan", "cookies and cream", "rainbow" ]
  toppings = [ "gummi bears", "hot fudge", "butterscotch", "rainbow sprinkles", "chocolate sprinkles" ]
  ```
<details>
  <summary>
    Hint
  </summary>
  Use nested enumerable methods or check out <a href="http://apidock.com/ruby/Array/product">product</a>.
</details>

### Map (30 minutes)

#### Explore 1

Run these two snippets separately:

```rb
cart = ["shoes", "watch", "computer"]
uppercase = cart.each do |product|
  caps_product = product.upcase
  puts caps_product
  caps_product
end
puts uppercase.join(", ")
```

```rb
cart = ["shoes", "watch", "computer"]
uppercase = cart.map do |product|
  caps_product = product.upcase
  puts caps_product
  caps_product
end
puts uppercase.join(", ")
```

<details>
<summary>How would you explain the difference in the result?</summary>
<ul>
  <li><code>.each</code> executes the code block for each item in the original array and returns the original array regardless of what the block returns.</li>
  <li><code>.map</code> returns a new array with the changes in the block applied to each element.</li>
</ul>
</details>

#### Explore 2

Consider:

```ruby
cart = ["shoes", "watch", "computer"]
uppercase = []
cart.each{|product| uppercase.push(product.upcase) }
puts uppercase.join(", ")
```

```rb
cart = ["shoes", "watch", "computer"]
uppercase = cart.map{|product| product.upcase }
puts uppercase.join(", ")
```

<details>
<summary>What is the difference in the result of these two snippets?</summary>
Nothing: they have the same result. They are two ways of doing the same thing.
</details>

#### Explore 3: Bang

Consider:

```rb
cart = ["shoes", "watch", "computer"]
uppercase = cart.map{|product| product.upcase }
puts cart
puts uppercase
```

Below is the same snippet, but with `.map!` instead of `.map`.

<details>
<summary>What does <code>!</code> often indicate in Ruby?</summary>
That this method is "dangerous", usually because it will modify, or <strong>mutate</strong> the object upon which it was called.
</details>

```rb
cart = ["shoes", "watch", "computer"]
uppercase = cart.map!{|product| product.upcase }
puts cart
puts uppercase
```

<details>
<summary>What's the difference between <code>.map</code> and <code>.map!</code>?</summary>
<code>.map</code> leaves the original array alone, whereas <code>.map!</code> changes it.
</details>

### Exercise: Practice Map (15 minutes)

Use `map` to do the following...  

1. Create an array that appends "Duck" to everybody in this array of first names

  ```ruby
  first_names = [ "Donald", "Daisy", "Daffy" ]

  #= ["Donald Duck", "Daisy Duck", "Daffy Duck"]
  ```

2. Create an array containing the squared values of every number in this array.

  ```ruby
  numbers = [ 1, 3, 9, 11, 100 ]

  # => [1, 9, 81, 121, 10000]
  ```

3. Create an array with the Celsius values for these Fahrenheit values.

  > Hint: `C = (F - 32) * (5 / 9)`

  ```ruby
  fahrenheit_temps = [ -128.6, 0, 32, 140, 212 ]

  #=> [-89.2, -17.8, 0, 60, 100]
  ```

<!--
## Methods

As stated before, everything in Ruby is an object so there is no distinction in this language between functions and methods. Under the hood, even seemingly stand-alone functions are in fact associated with an object. The convention, however, is to call these methods.

**We use the word `method` in Ruby, never `function`. If we do it's mostly out of habit.**

A method is made up of a few components. Take a look at the following method.
```ruby
def double( number )
   doubled_number = number * 2
   return doubled_number
end  

double( 3 )
# => 6

double 3
# => 6
```

This method has several components to point out: 
 - def - the Ruby equivalent of function
 - double - the method name in the below example
 - number - the argument name in the below example
 - end - closes the method

Passing arguments in Ruby works fairly similar to how it does in JS. They get passed as comma separated values after the method name.

```ruby
def hello(name, greeting, small_talk, punctuation)
  "#{greeting} #{name}, #{small_talk}#{punctuation}"
end
```

Lets think back to the behaviors of arguments in JS.  Remember how lenient it is?

In Ruby, if you specify a number of arguments, the function must take that number of arguments. No more, No less. 

### Less
```ruby
$ hello("Jamie", "Hark", "frickin' cold eh")

=> ArgumentError: wrong number of arguments (given 3, expected 4)
```

### More
```ruby
$ hello("Jamie", "Hark", "frickin' cold eh", ".", "Forsooth, ye yonder pilgrim is quite the bespoke son of a tailors daughter, ai?")

=> ArgumentError: wrong number of arguments (given 5, expected 4)
```

SIDENOTE: Ruby's errors are amazing. Use them!

There are some fun ways to play with arguments and define further behavior:

### Default arguments

```ruby
def drink_milk(thirsty = true)
  return "I'm not thirsty" unless thirsty

  "mmmmmm... milk...."
end
```

### Woah, that return statement?

In Ruby, returns are implicit by design. Ruby will always assume that the last line of the method will be returned. So why the first return?

Can you read it in English? One of Ruby's biggest benefitsis that it reads pretty closely to English

Additionally, you can add the statements `if` and `unless` to your return statement, which acts similarly to an if block.

```javascript
function apiCall(err, data){
  if (err){
    return err;
  } 
  //Do stuff
}
```

vs.

```ruby
def api_call(err, data)
  return err if err
  #Do Stuff
end
```

### Everything is an Expression

```ruby
def add(a, b)
  a + b
end

add(1, 2) # => 3

add(1, 2, 3)
# > ArgumentError: wrong number of arguments (given 3, expected 2)
```

Notice we do not need the keyword ```return```. The last line hit by the method will always be the return value. This is called an implicit return.


-->
### Predicate Methods (?)

This is similar to adding the bang to the end of a method. Predicate methods using `?` returns a boolean value.
```ruby
  5.odd?
  # true
  5.even?
  # false
  something = "A thing"
  # => "A thing"
  something.nil?
  # => false
``` 
## Ruby Code Style Guide

The Ruby community is very opinionated about styling.  As you are starting out, you MUST follow [these rules](https://github.com/bbatsov/ruby-style-guide).

Here are the most important rules

**Casing**

* All variables and methods must use `snake_case`
* All classes and modules must use `CamelCase`
* All constants (besides classes and modules) must use `SCREAMING_SNAKE_CASE`

**Blocks**

* A single line block must use `{` and `}`
* A multi-line must use `do` and `end`
* If an argument is unused it should start with `_` (or just be named `_`)
  * `hash.each { |_key, val| puts val }`
<!--
**Methods**

* A method should end with a `?` if an only if it always returns a boolean
  * These are called _predicate methods_
* A method ending in `!` should be a _dangerous_ version of the method sans `!`
  * _dangerous_ means either that it can mutate the object _or_ that can raise an error
* Don't name methods like `get_foo`, `set_foo`. They should be `foo` and `foo=`
* **Do** use `attr_reader` and `attr_writer`
* Do not use parens when calling a method without args
  * `super` is one possible exception
* **Do** use parens for every method except for DSLs (and a small list of other common methods)
  * `attr_reader`, `puts`, `require`, `include`, `it`, `has_many`, ...
-->

