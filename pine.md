Key concepts from Pine's Learn to Program
=========

* Why is programming hard?  Because you have to explain "everything" in terms the computer can understand.

* Programs grow, they do not emerge fully formed; they are tweaked, revised, rewritten, deleted, refactored.  They grow slowly and painfully over time

* Avoid duplication - keep code DRY (Don't Repeat Yourself) - don't force yourself to need to update the same bits of code in multiple locations

* Ch.2 Numbers
 - puts method
 - Difference between integers and floats
 - Unexpected integer division result

* Ch.3 Letters
 - Strings
 - Empty string
 - String multiplication
 - Numbers vs digits, i.e. 12 vs '12'
 - Error message: #<TypeError: can't convert Fixnum into String>
 - Operator order (5 * 'pig' vs 'pig' * 5)
 - Escaping apostrophes, and escape operator generally

* Ch.4 Variables and Assignment

 - variable assignment (var1 = 1)
 - lower case variables
 - variable re-assignment (var1 = 2)
 - variables assigned to each other (var1 = var2)

* Ch.5 Mixing it up

 - .to_s, .to_i, .to_f operators
 - puts uses .to_s
 - gets method
 - chomp method
 - "#<TypeError: can't convert Fixnum into String>" - difference between Fixnums and Bignums, explains the error message

* Ch.6 More about methods

 - methods are 'verbs' to object 'nouns'
 - arithmetic operators are also methods
 - introducing the '.' operator ('5 + 5' <=> '5.+ 5')
 - self
 - String#reverse String#length non-destructive methods
 - String#upcase, downcase, swapcase, capitalize
 - center, ljust, rjust methods
 - optional maths section
   - %, \*\*, abs, rand, srand
   - Math object (Math::PI, Math::E, Math#cos, Math#sin, Math#tan, Math#log, Math#sqrt)

* Ch.7 Flow Control

 - <, >, true, false, >=, <=, ==, !=
 - branching with 'if ... end'
 - importance of indentation
 - else
 - nested if statements
 - comments as # - well written code speaks for itself
 - while loops
 - Ctrl-c to break out of loops
 - elsif
 - ||, &&, !

* Ch.8 Arrays and Iterators

 - Arrays []
 - referencing arrays
 - Array#each
 - 'do ... end' blocks
 - variables in blocks |var|
 - Fixum#times method
 - Array#length, Array#reverse, Array#+, Array#\*, Array#last, Array#join, Array#to_s, Array#push, Array#pop, Array#sort

* Ch.9

 - method definitions (def ... end), method names start with lower case
 - method parameters
 - local variables and scope
 - global scope
 - return values (explicit vs implicit)

* Ch.10

 - recursion
 - sorting

* Ch.11

 - File#open, File#read
 - YAML
 - String#to_yaml
 - YAML::load
 - double quoted strings, string interpolation
 - Dir
 - Dir.chdir
 - File.rename

* Ch.12
 - class names are capitalized
 - Object.new method
 - Time class
 - Hash class
 - Range class
 - String#[]

* Ch.13
 - monkey patching
 - creating new classes
 - instance variables
 - initialize method
 - private

* Ch.14
 - more on blocks
 - Proc
 - &block

Notes
----
* editor recommendation currently sublime? atom?
* IRB not in general use
* tracking for exercises?
* pre-interview students told to do up to chapter 8
* work out how much of LO are covered - and then, should continue Pine?  something else?
* exercises in ch.10 onwards could take a little time, but reasonably interesting
* doesn't cover symbols, lambdas, gems
