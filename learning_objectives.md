*Learning Objectives are extracted here on a topic-by-topic basis (like the main course).*

## Week 1

## Dev Skills

### [Development setup](http://www.preparetocode.io/)
- Manually set up a computer for web development
  - Install XCode
  - Install Homebrew
  - Install RVM and Ruby
  - Install Pry

### [Atom](pills/installing_atom.md)
- Know that Atom is an editor for altering many different file types
- Install Atom
- Use Atom to make changes to files
- Symlink Atom for rapid opening from the command line

### [Command Line](pills/command_line.md)
- Explain that the command line allows direct access to a computer's underlying code
- Use simple command line commands, such as `ls`, `pwd`, and `cd`
- Use flags to enhance command abilities
- Manipulate files from the command line
- Modify permissions in a filesystem
- Update a ./profile file
- Consider using `vi` to alter files

### [Git](pills/git.md)
- Recall that git is a version control system (VCS)
- Recognise common git commands, such as `fetch`, `merge`, `clone`, `pull`, `push`, `add`, `remote`, and `commit`
- Explain the following terms: 'staging', 'branching', 'upstream', 'remote'
- Explain how repos work, referencing the `.git` file
- Explain how git branching works
- Fork a git repo
- Clone a git repo
- Add files for staging in a git repo
- Commit staged files in a git repo
- Create a new topic branch locally
- Push files to a remote repo
- Make a pull request to an upstream repo

## Weeks 2 - 4

## Ruby

### [Pairing](pills/pairing.md)
- Know some rules of thumb for great pairing
- Get started with pair programming

### [`irb`](https://blog.makersacademy.com/playing-in-irb-34e5498f7cd5#.ie88896w1)
- Recall that `irb` means 'interactive Ruby shell'
- Explain how `irb` is a [Read-Eval-Print-Loop (REPL)](http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)
- Use `irb` to experiment with Ruby

### [Strings](pills/strings.md)
- Define 'String' as an object holding an arbitrary number of (usually) characters
- Explain how to create new Strings
- Use common String methods such as `concat`, `upcase`, and `chars`

  [Codewars Katas - Strings](https://www.codewars.com/kata/search/ruby?beta=false&q=&tags=Strings&xids=played)   
  [HackerRank - Strings Challenges](https://www.hackerrank.com/domains/ruby/ruby-strings)


### [Variables](pills/variables.md)
- Define variables as assigned values using the = operator
- Explain how to create new new variables
- Use variables to hold different types of values

  [Codewars Katas - Variables](http://www.codewars.com/kata/search/ruby?q=variables&r%5B%5D=-8&r%5B%5D=-7&beta=false)


### [Methods](pills/methods.md)
- Define a method as a way of automating Ruby commands
- Relate methods to writing DRY code
- Implement methods to solve simple problems

  [Codewars Kata -  Methods](http://www.codewars.com/kata/search/ruby?q=method&r%5B%5D=-8&beta=false)


### [Booleans](pills/boolean.md)
- Know that 'boolean' refers to either `true` or `false`
- Explain that everything in Ruby is 'truthy', except `false` or `nil`, which are 'falsy'
- Explain ideas of 'truthy' and 'falsy'

  [Codewars Katas - Booleans ](http://www.codewars.com/kata/search/my-languages?q=boolean&r%5B%5D=-8&beta=false)

### [Arrays](pills/arrays.md)

- Define array as indexed collection of related items
- Explain square-bracket notation
- Use array methods such as `first`, `include?`, `select`, `map`, and iterators like `each` and `inject`

  [Codewars Katas - Arrays](http://www.codewars.com/kata/search/ruby?q=array&r%5B%5D=-8&beta=false)


### [Control Flows](pills/control_flow.md)
- Remember that 'control flows' are statements that control the flow of a program
- Use `if`/`else` statements to build conditional execution flows
- Connect the idea of [booleans](pills/boolean.md) with conditional statements in control flows
- Use more terse versions of control flows (such as inline `if` statements, `else` statements, and ternary operators)
- Analyse when to swap `if`/`else` statements for 'switch' statements

  [Codewars Katas - Control Flow](http://www.codewars.com/kata/search/ruby?q=control+flow&r%5B%5D=-8&beta=false)

### [Symbols](pills/symbols.md)
- Define Symbols as String-like objects that are **immutable**
- Explain how Symbols' immutability makes them very memory-efficient
- Use Symbols within Hashes as keys

  [Codewars Katas - Symbols](http://www.codewars.com/kata/search/ruby?q=symbol&r%5B%5D=-8&r%5B%5D=-7&beta=false)

### [Hashes](pills/hashes.md)
- Define a hash as a 'dictionary' or 'associative array'
- Give the structure of a hash as `{ :key => value }` or `{ key: value }`
- Use Ruby hashes to solve code Katas

  [Codewars Katas - Hashes](http://www.codewars.com/kata/search/ruby?q=hash&r%5B%5D=-7&r%5B%5D=-8&beta=false)

### [Blocks](pills/blocks.md)
- Recall the structure of blocks using both `{}` and `do..end` notation
- Explain how blocks are used in Ruby
- Demonstrate appropriate use of blocks for readability

  [Codewars Katas - Blocks](http://www.codewars.com/kata/search/ruby?q=block&r%5B%5D=-8&beta=false)

### [Recursion](pills/recursion.md)
- Define recursion in Ruby as being when a method calls itself
- Explain how to avoid infinite recursion loops
- Use recursion to avoid nesting loops

  [Codewars Katas - Recursion](http://www.codewars.com/kata/search/ruby?q=recursion&r%5B%5D=-8&r%5B%5D=-7&r%5B%5D=-6&beta=false)


### [User Interaction](pills/user_interaction.md)
- Explain how to get user input using `gets`
- Sanitize user input using `chomp` and `chomp!`

### [Gems](pills/gems.md)
- Define a ruby gem as a reusable ruby library
- State scenarios where gems are used
- Remember where to find gems
- Explain how to install gems

### [Lambdas](pills/lambdas.md)
- Recognise the structure of a `lambda`
- Explain that lambdas are 'anonymous methods' in Ruby
- Use lambdas to solve basic metaprogramming problems

  [Codewars Katas - Lambdas](http://www.codewars.com/kata/search/ruby?q=lambdas&r%5B%5D=-8&r%5B%5D=-7&beta=false)

### [Procs](pills/procs.md)
- Define a Proc as another 'anonymous method' in Ruby
- Link Procs with lambdas
- Implement a Proc, pass it as a parameter, and call it
- Solve metaprogramming problems with Procs

  [Codewars Kata- Lambdas](http://www.codewars.com/kata/search/ruby?q=procs&r%5B%5D=-8&r%5B%5D=-7&r%5B%5D=-6&beta=false)


### Tips and tricks

##### [Parallel Assignment](pills/parallel_assignment.md)
- Recall what parallel assignment is
- Explain why parallel assignment is useful

##### [Shovel Operator](pills/shovel_operator.md)

- Recall what the ['shovel operator'](pills/shovel_operator.md) is
- Explain how to use the ['shovel operator'](pills/shovel_operator.md)

##### [String Interpolation](pills/string_interpolation.md)
- Recall what string interpolation is
- Explain how to use string interpolation
- Use string interpolation to solve code Katas

  [Codewars Katas - String Interpolation](http://www.codewars.com/kata/search/ruby?q=interpolation&r%5B%5D=-8&r%5B%5D=-7&r%5B%5D=-6&beta=false)
