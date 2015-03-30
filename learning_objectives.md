*Learning Objectives are extracted here on a topic-by-topic basis (like the main course).*

##Ruby

###[Arrays](pills/arrays.md)
- Define array as indexed collection of related items
- Explain square-bracket notation
- Use array methods such as `first`, `include?`, `select`, `map`, and iterators like `each` and `inject`

###[Blocks](pills/blocks.md)
- Recall the structure of blocks using both `{}` and `do..end` notation
- Explain how blocks are used in Ruby
- Demonstrate appropriate use of blocks for readability

###[Booleans](pills/boolean.md)
- Know that 'boolean' refers to either `true` or `false`
- Explain that everything in Ruby is 'truthy', except `false` or `nil`, which are 'falsy'
- Explain ideas of 'truthy' and 'falsy'

###[Control Flows](pills/control_flow.md)
- Remember that 'control flows' are statements that control the flow of a program
- Use `if`/`else` statements to build conditional execution flows
- Connect the idea of [booleans](pills/boolean.md) with conditional statements in control flows
- Use more terse versions of control flows (such as inline `if` statements, `else` statements, and ternary operators)
- Analyse when to swap `if`/`else` statements for 'switch' statements

###[Gems](pills/gems.md)
- Define a ruby gem as a reusable ruby library
- State scenarios where gems are used
- Remember where to find gems
- Explain how to install gems

###[Hashes](pills/hashes.md)
- Define a hash as a 'dictionary' or 'associative array'
- Give the structure of a hash as `{ :key => value }` or `{ key: value }`
- Use Ruby hashes to solve code Katas

###[`irb`](pills/irb.md)
- Recall that `irb` means 'interactive Ruby shell'
- Explain how `irb` is a REPL
- Use `irb` to experiment with Ruby

###[Lambdas](pills/lambdas.md)
- Recognise the structure of a `lambda`
- Explain that lambdas are 'anonymous methods' in Ruby
- Use lambdas to solve basic metaprogramming problems

###[Methods](pills/methods.md)
- Define a method as a way of automating Ruby commands
- Relate methods to writing DRY code
- Implement methods to solve simple problems

###[Procs](pills/procs.md)
- Define a Proc as another 'anonymous method' in Ruby
- Link Procs with lambdas
- Implement a Proc, pass it as a parameter, and call it
- Solve metaprogramming problems with Procs

###[Recursion](pills/recursion.md)
- Define recursion in Ruby as being when a method calls itself
- Explain how to avoid infinite recursion loops
- Use recursion to avoid nesting loops

###[RVM](pills/installing_rvm.md)
- Recall that 'RVM' is 'Ruby Version Manager'
- Use RVM to install a new version of Ruby
- Use RVM to manage the current version of Ruby

###[Strings](pills/strings.md)
- Define 'String' as an object holding an arbitrary number of (usually) characters
- Explain how to create new Strings
- Use common String methods such as `concat`, `upcase`, and `chars`

###[Symbols](pills/symbols.md)
- Define Symbols as String-like objects that are **immutable**
- Explain how Symbols' immutability makes them very memory-efficient
- Use Symbols within Hashes as keys

###[User Interaction](pills/user_interaction.md)
- Explain how to get user input using `gets`
- Sanitize user input using `chomp` and `chomp!`

###[Variables](pills/variables.md)

###Tips and tricks

#####[Parallel Assignment](pills/parallel_assignment.md)
- Recall what parallel assignment is
- Explain why parallel assignment is useful

#####[Shovel Operator](pills/shovel_operator.md)

- Recall what the ['shovel operator'](pills/shovel_operator.md) is
- Explain how to use the ['shovel operator'](pills/shovel_operator.md)

#####[String Interpolation](pills/string_interpolation.md)
- Recall what string interpolation is
- Explain how to use string interpolation
- Use string interpolation to solve code Katas

##Dev Skills

###[Development setup](pills/installation_instructions.md)
- Manually set up a computer for web development
- Discover a quicker way to set up a computer for web development

###[Command Line](pills/command_line.md)
- Explain that the command line allows direct access to a computer's underlying code
- Use simple command line commands, such as `ls`, `pwd`, and `cd`
- Use flags to enhance command abilities
- Manipulate files from the command line
- Modify permissions in a filesystem
- Update a ./profile file
- Consider using `vi` to alter files

###[Git](pills/git.md)
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

###[Pairing](pills/pairing.md)
- Know some rules of thumb for great pairing
- Get started with pair programming

###[Sublime](pills/installing_sublime.md)
- Know that Sublime Text is an editor for altering many different file types
- Install Sublime Text
- Symlink Sublime Text for rapid opening from the command line
- Use Sublime Text to make changes to files

###[XCode](pills/installing_xcode.md)
- Install XCode