# Methods in Ruby

## Learning Goals

- Demonstrate abstraction with methods
- Define DRY
- Recognize the structure of a method
- Recognize how to call methods
- Practice method calls
- Identify common programming conventions

## Introduction

_Methods_ are used to bundle one or more activities into a single unit. In daily
life we do this all the time: "get ready for work" means: "take a shower, walk
the dog, eat breakfast." But each of _those_ activities are made up of other
sub-activities, and sub-sub activities.  Take a shower involves steps like "wash
hair" which itself has steps like "wet head under shower", "apply shampoo", etc.

Nearly all programming languages have the idea of "bundling up work" under a
programmer-created name. While different languages might call them
"subroutines," "methods," or "functions," they all mean the same thing: grouping
work.

In this lesson we'll introduce methods, distinguish them from data types, and
cover how to create and execute them in your Ruby program.

## Demonstrate Abstraction With Methods

Methods define a new thing that your program can do. While variables in Ruby store
data, methods store a new routine or behavior your program can use. Variables
are like "nouns", a thing, and methods are like "verbs", an action.

For example, imagine needing to say "Hello World!" five times. It could look
like this:

```ruby
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
```

That technically works. You made use of a variable to store the data you wanted
to output, and then the next five lines output the phrase.

Now imagine later in your program you want to say "Hello World!" five times
again. We would have to write "Hello World!" five more times.

If we wanted to use a method to contain this actions, it could look like this:

```ruby
def say_hello_world_five_times
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
end
```

Now, when we use the word `say_hello_world_five_times` in our program, it
will invoke the method, running the code within the method. So the script above,
saying hello five times, doing other things, then saying hello five times again
could be rewritten as this:

```ruby
def say_hello_world_five_times
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
end
```

This is much cleaner. We _abstracted_ the action or procedure of putting "Hello
World!" five times into a method.

## Define DRY

DRY stand for "Don't Repeat Yourself," a basic principle of software development
aimed at reducing repetition of information. Less code is good: It saves time
and effort, is easy to maintain, and also reduces the chances of bugs.

We abstracted the action or procedure of printing "Hello World!" five times into
a method. By defining the method `say_hello_world_five_times` once, we can
"call" or "invoke" the method as many times as we want in the future. Let's look
at methods in greater detail.

## Recognize the Structure of a Method

When we define a method in Ruby, we use the `def` keyword. A method's name should
begin with any lowercase letter.

This defines a method. It does not use it -- yet: This is the first step so that
it can be used later.

```ruby
def say_hello_world
  puts "Hello World!"
end
```

The first line of `def say_hello_world` is called the method signature, it
defines the basic properties of the method including the name of the method,
`greeting`.

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

Remember earlier where we defined the method, but it didn't run the work in the
method yet. Here's where we do that! Once you define a method, you can execute
the method whenever you want by using the method name in your code. Methods
should be defined before calling them, otherwise Ruby will raise an exception
for undefined method invoking.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#> "Hello World"

greeting # Executing the method again
#> "Hello World"
```

## Practice Method Calls

Let's try it out, step by step. Create a new file called `greeting.rb`. You can
use: `touch greeting.rb` from your terminal to do so. Paste the following code
into `greeting.rb`:

```ruby
def greeting
  puts "Hello World"
end
```

If you save your file and try to run it with `ruby greeting.rb`, you'll see:

```bash
$ ruby greeting.rb
$
```

You'll notice that when you run your program, there is no output and nothing
happens. We successfully defined the method, but never executed it anywhere in
the code. It's like we screwed in a new lightbulb, but haven't turned it on.
Update the code in `greeting.rb` to read:

```ruby
def greeting
  puts "Hello World"
end

greeting
```

Now we've called the method at the bottom our file. Save this file and run it
with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
Hello World
$
```

Now your program actually executed the code in the method! Now let's update the
code in `greeting.rb` again to the following:

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

Now we've written `greeting` five times at the bottom of the code. Save your
file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
Hello World
Hello World
Hello World
Hello World
Hello World
$
```

The bareword `greeting` will execute the body of the defined method for each
time it was called.

## Identify Common Programming Conventions

Programmers love conventions, or agreed upon rules that help them talk to each
other about code. A common syntax convention for Ruby methods is to preface them
with a `#`, and in subsequent lessons, you might see methods written with a `#`
in front of the method name. For example, if a method is named 'greeting',
rubyists will often refer to it as `#greeting`. This is so that other rubyists
can instantly recognize it as a method, as opposed to a variable or a bareword
or a class.  But remember that when you write it in your code, it should be
`greeting` and not `#greeting`.

## Conclusion

Methods are a big part of programming in Ruby. We use them to save and perform
repeatable actions. Knowing how to define and call methods is crucial to
building programs, as well as your development as a programmer. You'll have to
use them often, in big or small programs.

## Resources
[Ruby Programming/Syntax/Method Calls](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls)
[Ruby - Methods](https://www.tutorialspoint.com/ruby/ruby_methods.htm)
[Ruby Methods](https://www.w3resource.com/ruby/ruby-methods.php)