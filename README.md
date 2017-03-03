# Ruby 101

Ruby is a dynamic programming language with a focus on simplicity and productivity. It has an elegant syntax that is natural to read and easy to write.

## How to run your code

1. In IRB

   You can run `$ irb` in the terminal to launch a Ruby interpreter. You can see it as a playground to test things out.

2. Using Ruby files

   Using Ruby files, for example `wagon.rb`. Launch your Ruby script from the terminal with:

   ```bash
   $ ruby path/to/your/file.rb
   ````

## Built-in Ruby Objects

Everything in Ruby is an object. Objects have in-build methods you can call on them.

### Strings

- To represent text
- Defined with single quotes or double quotes: `'wagon'` or `"wagon"`

```ruby
"wagon".class        # => String
"wagon".upcase       # => "WAGON"
"wagon".capitalize   # => "Wagon"
```

- You can inject Ruby code into a string using interpolation, but in double-quoted strings

```ruby
'two: #{1 + 1}'      # => "two: #{1 + 1}"
"two: #{1 + 1}"      # => "two: 2"
```

- You can convert strings to numbers

```ruby
'1984'.class         # => String
'1984'.to_i          # => 1984
'1984'.to_i.class    # => Fixnum
```

### Fixnums

- To represent integers
- Can do standard arithmetic

```ruby
4.class              # => Fixnum
1 + 2                # => 3
2 * 4                # => 6
```

- Also has custom methods built-in

```ruby
20.even?             # => true
20.odd?              # => false
```

- You can convert numbers to strings

```ruby
1984.to_s          # => "1984"
```

### Floats

- To represent decimal numbers

```ruby
3.14.class         # => Float
1.23 + 2.1         # => 3.33
```

- Has it's own built-in methods

```ruby
3.14.round         # => 3
```

### Arrays

- To represent list of elements, usually of the same type
- Defined with square brackets around the list of items

```ruby
["paris", "london", "new york"].class     # => Array
[2, 5, 8, 2].class                        # => Array
```
- Has it's own built-in methods

```ruby
["paris", "london", "new york"].size      # => 3
["paris", "london", "new york"].sort      # => ["london", "new york", "paris"]
[3, 5, 1].sort                            # => [1, 3, 5]
```

<!-- CRUD -->

### Ranges

- To represent ranges of elements (usually numbers)
- Defined with `..` between two elements and brackets, `...` to exclude the last element from the range

```ruby
(1..5).class       # => Range
(1..5).to_a        # => [1, 2, 3, 4, 5]
(1...5).to_a       # => [1, 2, 3, 4]
("a".."e").to_a    # => ["a", "b", "c", "d", "e"]
```

### Booleans

- To represent something that is true or false

### Hashes

<!-- Hashes -->

### Built-in methods

The built in methods are well-documented, don't reinvent the wheel...

- [String methods](https://ruby-doc.org/core-2.3.3/String.html)
- [Fixnum methods](https://ruby-doc.org/core-2.3.3/Fixnum.html)
- [Floats methods](https://ruby-doc.org/core-2.3.3/Float.html)
- [Array methods](https://ruby-doc.org/core-2.3.3/Array.html)
- [Hash methods](https://ruby-doc.org/core-2.3.3/Hash.html)
- [Enumerable methods](https://ruby-doc.org/core-2.3.3/Enumerable.html)

## Variables

- Allows you to store values to reuse them later
- You **assign** a value to a variables
- Variables can be overwritten and incremented

```ruby
age = 21
puts "You are #{age} years old"

age = age + 1
puts "You are now #{age}"
```

```ruby
first_name = "Alex"
last_name = "Benoit"

puts "My name is #{first_name} #{last_name}"
```

## Methods

- Concise way to call Ruby code multiple times
- Apply the ruby code to dynamic inputs
- Defined with **parameters** and called with **arguments**
- A method always returns a result, and you can then operate on what is returned

```ruby
def full_name(first_name, last_name)
  name = "#{first_name.capitalize} #{last_name.capitalize}"
  return name
end

puts full_name("boris", "paillard")
```

- In the example above, `first_name` and `last_name` were parameters and `"boris"` and `"paillard"` were the arguments, and we `puts` what returned from the method call
- We can call the method with variables too

```ruby
my_first_name = "alex"
my_last_name = "benoit"
puts full_name(my_first_name, my_last_name)
```

- Methods ending with `?` such as `even?` and `start_with?` return a Boolean

## Flow Control

Conditionals and loops change the flow of a Ruby program. Conditionals allow us to execute a certain chunk of code under a specific condition. Loops allow us to execute a chunk of code multiple times. When the program is run, the code is executed from top to bottom, line by line, which is how you should debug in your head.

### Conditionals (If/Unless/Else)

#### If

```ruby
if condition
  # code executed only when condition is "truthy"
end
```

#### Unless

```ruby
unless condition
  # code executed only when condition is not "truthy"
end
```

#### If/Else

```ruby
if condition
  # code executed only when condition is "truthy"
else
  # code executed only when condition is not "truthy"
end
```

For example, a small Ruby program that checks if you are old enough to vote:

```ruby
puts "How old are you?"
age = gets.chomp.to_i

if age >= 18
  puts "You can vote!"
end
```

#### If/Elsif/Else

```ruby
if first_condition
  # code executed only if first condition is "truthy"
elsif second_condition
  # code executed only if second_condition is "truthy" and first_codition is not "truthy"
elsif third_condition
  # ...
else
  # code executed if no conditions are "truthy"
end
```

For example, a small Ruby program that greets you depending on the hour of the day:

```ruby
puts "What time is it?"
hour = gets.chomp.to_i

if hour < 12
  puts "Good morning!"
elsif hour >= 12 && hour < 20
  puts "Good afternoon!"
else
  puts "Good night!"
end
```

#### Combining condition

You can combine condition with `&&` which is the logical AND, or `||` which is the logical OR.

### While
