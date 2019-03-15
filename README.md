# Methods in Ruby

## Learning Goals

- Demonstrate abstraction with methods
- Define DRY
- Recognize the structure of a method
- Recognize how to call methods
- Practice method calls

## Introduction

_Methods_ are used to bundle one or more activities into a single unit. In
daily life we do this all the time: "get ready for work" means: "take a shower,
walk the dog, eat breakfast." But each of _those_ activities are made up of
other sub-activities, and sub-sub activities.  "Take a shower" involves steps
like "wash hair" which itself has steps like "wet head under shower", "apply
shampoo", etc.

Nearly all programming languages have the idea of "bundling up work" under a
programmer-created name. While different languages might call them
"subroutines," "methods," or "functions," they all mean the same thing:
grouping work under a name that _we_ think is appropriate.

In this lesson we'll introduce methods, distinguish them from data types, and
cover how to create and execute them in your Ruby program.

## Demonstrate Abstraction With Methods

Methods define a new thing that your program can do. While variables in Ruby
store data, methods store a new routine or behavior your program can use.
Variables are like "nouns", things, and methods are like "verbs," actions.

For example, imagine needing to say "Hello World!" five times. It could look
like this:

```ruby
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
```

This meets the requirement alright.  Now imagine that later in your program you
want to say "Hello World!" five times _again_. We would have to write "Hello
World!" five more times.


```ruby
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"

# Other work here....

puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
puts "Hello World!"
```

But we're repeating the same `String` over and over. Let's put that message as
variable called, helpfully, `message`.

```ruby
message = "Hello World!"
puts message
puts message
puts message
puts message
puts message

# Other work here....

puts message
puts message
puts message
puts message
puts message
```

Here we made use of a variable to store the message, and didn't change anything
else.  You should be able to see here that by doing this our code is easier to
change. From "Hello World!" we could easily go to "Hola Mundo!" by making _one_
change versus making _10_ changes.

But all those `puts` appearing multiple times...there's something...that
bothers our programmer brains about this. It's seeing _so much repetition_.

![We sense something wrong about this](https://gph.is/2AinZom)

Could we reduce the repetition somehow?

If we created a method to contain this "saying `message` five times action" we
could get rid of some of that repetition.

Here's the method...

```ruby
def say_hello_world_five_times
  message = "Hello World!"
  puts message
  puts message
  puts message
  puts message
  puts message
end
```

And, once integrated, our code could be much simpler:


```ruby
def say_hello_world_five_times
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
  puts "Hello World!"
end

say_hello_world_five_times
# other work
say_hello_world_five_times

```

Now, when we use the word `say_hello_world_five_times` in our program, it
will invoke the method, running the code within the method.

This is cleaner. Programmers would say "We _abstracted_ the 'action,' or
'procedure,' of `puts`-ing 'Hello World!' five times into a method." Later, we'll
see ways of making this code _even more_ abstract.

## Define DRY

DRY stand for "Don't Repeat Yourself," a basic principle of software development
aimed at reducing repetition of information. Less code is good: It saves time
and effort, is easy to maintain, and also reduces the chances of bugs. When we
see unsophisticated repetition, we want to reach for a form of _abstraction_.
Creating methods is a common and powerful tool of abstraction.

> Numerous doctoral research projects have looked at the relationship between
> lines of code and bugs. It turns out the only significant predictor of fewer
> bugs is..._fewer lines of code_!

## Recognize the Structure of a Method

Let's put a method's definition here so we can learn its parts:

```ruby
def say_hello_world
  puts "Hello World!"
end
```

When we define a method in Ruby, we use the `def` keyword. A method's name
should begin with a lowercase letter.

The first line of `def say_hello_world` is called the method _signature_, it
defines the basic properties of the method including the name of the method,
`greeting`. We'll learn more about the other properties later.  The name of a
method should suggest what it does. If you need multiple words, Rubyists use a
`_` to separate them. Separating words by underscore (`_`) is called
_snake-case_ (because the shape looks like the words were swallowed up by a
snake).

Once you begin a method definition with the `def` keyword, all following lines
_until_ the method's closing `end` keyword are called the method's _body_ or
the method's _implementation_. The _implementation_ is the actual code that your
method will run every time it's called.  It's standard practice to indent the
body by two spaces.

After multiple bits of work (expressions, variables set and looked up, etc.) we
must provide an `end` keyword.

> **TIP**: A good practice is to define the method and then immediately close
> it with `end` _before_ writing the _body_. Many expressions in Ruby use
> `do...end` and it can be confusing to keep them all straight. By creating the
> `def (name)`...`end` "bookends," and _then_ fillig out the implementation, 
> we help prevent possible confusion.
>
> ```ruby
> def greeting # type this first
>   # # Third: start typing your implementation
> end # type this second
> ```

Look at the method definition for `greeting` again and make sure it makes sense:

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

All this work _defines_ a method. It does not _run_ it &mdash; yet. We must
_define_ it before we can _use_.  Think of it like writing a recipe: writing
the recipe does not mean doing the work of preparing the dish. If it were that
easy, we'd all have much fancier dinners at home!

## Recognize How to Call Methods

We've written the method, let's _call_ it. Once you define a method, you can
_call_ or _execute_ the method whenever you want by using the method name in
your code.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#=> "Hello World"

greeting # Executing the method again
#=> "Hello World"
```

Some languages expect you to _call_ methods by typing (`greeting()`). Ruby doesn't
require this.

## Practice Method Calls

Let's code a method for ourselves, step by step. Create a new file called `greeting.rb`. You can
use: `touch greeting.rb` from your terminal to do so. Open up `greeting.rb` in
your editor and paste the following code
into it:

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
happens. We successfully _defined_ the method, but never _executed_ or _called_
it anywhere in the code. It's like we screwed in a new lightbulb, but never
flipped the switch to "on." Ruby reads your definition of `greeting` and then
says..."I'm done. Exit." Let's give it something to do before exiting: _call_
`greeting`.

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

Now your program _actually executed_ the code in the method! Let's update the
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

The word `greeting` will execute the body of the defined method for each
time it was called.

As a final step we could write a method to do the work of "say greeting five times:"

```ruby
def greeting
  puts "Hello World"
end

def say_greeting_five_times
  greeting
  greeting
  greeting
  greeting
  greeting
end

say_greeting_five_times
```

You shoudl start to see that bigger programs could be build of methods caling
sub-methods and those sub-methods calling sub-sub-methods &mdash; just like
we suggested in our example about "getting ready to go to work."


## Conclusion

Methods are a big part of programming in Ruby and pretty much _every_ language.
We use them to save and perform repeatable actions. Knowing how to define and
call methods is crucial to building programs, as well as your development as a
programmer. You'll have to use them often, in big or small programs.

## Resources
[Ruby Programming/Syntax/Method Calls](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls)
[Ruby - Methods](https://www.tutorialspoint.com/ruby/ruby_methods.htm)
[Ruby Methods](https://www.w3resource.com/ruby/ruby-methods.php)
