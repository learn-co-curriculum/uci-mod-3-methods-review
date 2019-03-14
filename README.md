# Methods in Ruby

## Learning Goals

- Describe routines and procedures for our code using methods
- Define a method
- Recognize how to call methods

## Introduction

A method in Ruby is a _block_ of code that returns a value. With methods, we can
organize our code into chunks of reusable functionality that can be easily used
by other areas of their program.

Ruby methods are very similar to functions in any other programming language.
Ruby methods are used to bundle one or more repeatable statements into a single
unit.

In this lesson we'll introduce methods, distinguish them from data types, and
cover how to create and execute them in your Ruby program.

## Describe Routines and Procedures for Our Code Using Methods

Methods define a new thing that your program can do. Variables in Ruby store
data; methods store a new routine or behavior your program can use. Variables
are like "nouns", a thing, and methods are like "verbs", an action.

For example, imagine needing to say "Hello World!" five times. It could look
like this:

```ruby
phrase = "Hello World!"
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
```

That technically works. You made use of a variable to store the data you wanted
to output, and then the next five lines output the phrase.

Now imagine later in your program you want to say "Hello World!" five times
again. We would have to output the value of `phrase` five times.

If we wanted to use a method to contain this actions, it could look like this:

```ruby
def say_hello_world_five_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end
```

Now, when we use the word `say_hello_world_five_times` in our program, it
will invoke the method, running the code within the method. So the script above,
saying hello five times, doing other things, then saying hello five times again
could be rewritten as this:

```ruby
def say_hello_world_five_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end
```

That's much cleaner and follows the code principle "don't repeat yourself" or
DRY. We abstract the action or procedure of putting "Hello World!" five times
into a method. By defining the method `say_hello_world_five_times` once, we can
"call" or "invoke" the method as many times as we want in the future. Let's look
at methods in greater detail.

## Define a Method

Method names should begin with a lowercase letter. If you begin a method name
with an uppercase letter, Ruby might think that it is a constant and hence can
parse the call incorrectly.

Suppose we need to define a simple method that outputs a string.

You can define a method in Ruby with the `def` keyword. A method's name can
begin with any lowercase letter. Here’s how we can do that:

```ruby
def greeting # Method Signature
  puts "Hello World" # Method Body
end # Method Closing
```

This defines a method. It does not use it -- yet: This is the first step so that
it can be used later.

Let’s walk through this method definition step by step:

That first line, `def greeting`, is called the method signature, it defines the
basic properties of the method including the name of the method, `greeting`.

Once you open a method definition with the `def` keyword, all subsequent lines
in your program are considered the method's body, the actual procedure or code
that your method will run every time it's called.

You must terminate every opening `def` of a method with a corresponding `end` in
order to close the method body. If you don't correctly `end` a method, your
program will have unexpected results or break entirely because of a syntax
error. A good practice is to define the method and then immediately close it
before programming anything into the method.

```ruby
def greeting
  # Leave a line break for the method body
end # Immediately close the method.
```

Here we set up the method's structure first, ensuring a proper termination
before adding any other complexity. It's also a great practice to indent methods
correctly. The body of a method should be indented two (2) spaces, placing it
visually within the method. When you `end` the method, go back to the same
indentation of the `def`, aligning the opening and closing of the method
visually.

Then you can easily define the body of the method and never worry about
forgetting to `end` the method.

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

## Recognize How to Call Methods

Once you define a method, you can execute the method whenever you want by using
the method name in your code. Methods should be defined before calling them,
otherwise Ruby will raise an exception for undefined method invoking.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#> "Hello World"

greeting # Executing the method again
#> "Hello World"
```

Try it out. Make a new file called `greeting.rb` (you can use: `touch
greeting.rb` from your terminal). Put the following code in it:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
$
```

You'll notice that when you run your program, nothing happens. Your program
successfully defined the method but it never executed it. Just because you built
a machine doesn't mean that you turned it on. Update your `greeting.rb` to
entirely read:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
Hello World
$
```

Now your program actually executed the program. Update the code again to
entirely read:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
greeting
greeting
greeting
greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
Hello World
Hello World
Hello World
Hello World
Hello World
$
```

The bareword `greeting` will execute the body of the defined method.

<SG: I don't think we need this?>
> Note: Programmers love conventions, or agreed upon rules that help them talk
> to each other about code. A common syntax convention for Ruby methods is to
> preface them with a `#`, and in subsequent lessons, you might see methods
> written with a `#` in front of the method name. For example, if a method is
> named 'greeting', rubyists will often refer to it as `#greeting`. This is so
> that other rubyists can instantly recognize it as a method, as opposed to a
> variable or a bareword or a class.  But remember that when you write it in
> your code, it should be `greeting` and not `#greeting`.

## Conclusion

Methods are a big part of programming in Ruby. We use them to save and perform
repeatable actions. Knowing how to define and call methods is crucial to
building programs, as well as your development as a programmer. You'll have to
use them often, in big or small programs.

## Resources
[Ruby Programming/Syntax/Method Calls](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls)
[Ruby - Methods](https://www.tutorialspoint.com/ruby/ruby_methods.htm)
[Ruby Methods](https://www.w3resource.com/ruby/ruby-methods.php)