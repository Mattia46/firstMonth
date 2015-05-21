Overview of Codecadeamy Ruby Track
==================================

Introduction to Ruby:
----------

###Intro

- Numbers, Strings, Booleans
- variables
- +, -, *, /, **, %
- puts and print
- objects and methods
  - String#length, String#reverse, String#upcase, String#downcase
- comments (single line, multi-line)
- variables start with lower case a-z

###Putting the Form in Formatter:

- String#capitalize!, String#upcase!
- String interpolation
- gets, String#chomp


Control Flow in Ruby
-----------

###Control Flow

- Integer
- true, false
- boolean operators (<, >, ==, !=, >=, <=, &&, ||, !)
- if ... elsif ... else ... end
- combining boolean operators
- unless
- precedence by parentheses


###Thith Meanth War

- String#include?, String#gsub!, String#downcase!
- simple regular expression /s/


Looping with Ruby
-----------

###Loops & Iterators

- while
- do ... end vs {}
- until
- +=
- for ... in
- ranges
- break
- next
- Arrays
- Array#each, |var| in block
- Fixnum#times

###Redacted

- String#split

Arrays & Hashes
------------

###Data Structures

- Array#[]
- arrays can contain strings and numbers
- multidimensional (nested) arrays
- Hashes, hash initialization via {}
- Hash#[], Hash#[]=
- Hash.new
- Hash#each, |key, value| in block
- review Array#each, |var| in block
- nested Array#each

###Create a Histogram

- Hash#reverse!, Hash#sort_by, Fixnum#to_s

Blocks & Sorting
-------------

###Methods, Blocks and Sorting

- methods - def ... end
- Object#is_a?
- Range#each
- method arguments
- Range#to_a
- explicit return
- Array#sort!
- spaceship operator <=>
- Array#sort! with block

###Ordering Your Library

- Array#sort
- default method arguments
- Array#reverse!

Hashes & Symbols
------------

###Hashes & Symbols

- hash literal notation versus hash constructor notation
- truthy, falsy, nil
- Symbol
- Object#object_id
- String#to_sym, String#intern
- 1.9 Hash syntax vs 1.8 Hash syntax (":k => v" - "k: v")
- Array#zip
- Hash[]
- Benchmark.realtime
- Hash#select, Hash#each_key, Hash#each_value

###A Night at the Movies

- case statement (case ... when ... else ... end)
- Object#nil?
- Hash#delete

Refactoring
-----------

###The Zen of Ruby

- one line if/unless
- ternary operator
- more on case statement
- conditional assignment '||='
- implicit return
- short circuit evaluation (|| & &&)
- Fixum#times vs Array#each
- Fixum#upto, Fixum#downto
- Object#respond_to?
- Array#<<
- string interpolation vs String#+ and String#<<

###The Refactor Factory

- refactoring code
- $GLOBALS
- Array#push
- Prime#instance

Blocks, Procs & Lambdas
---------------------

- review of blocks
- Array#collect, Array#collect!
- yield method
- yield with parameters
- creating procs with Proc.new
- '&' converts proc to block
- Proc#call
- &:method
- lambda method
- a lambda checks the number of arguments passed to it, while a proc does not
- when a lambda returns, it passes control back to the calling method; when a proc returns, it does so immediately, without going back to the calling method

Object Oriented Programming, Part 1
-----------------------------------

###OOP I

###Virtual Computer

Object Oriented Programming, Part 2
-----------------------------------

###OOP II

###Banking on Ruby


Notes:
------

* Interesting resource: http://www.codecademy.com/glossary/ruby
* Note still using old hash syntax
