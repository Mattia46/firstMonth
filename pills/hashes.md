# Hashes

Hash is another data structure that's widely used in Ruby. Sometimes called Dictionaries, Hashes are also a collection of elements, except that you can specify the indexes (or keys) you use to reference the elements. Consider this code:

````ruby
capitals = {"Great Britain" => "London", "France" => "Paris", "Germany" => "Berlin"}
````

This is very similar to an array, except we can use country names to reference the capitals. So, instead of `capitals[0]` we can now to `capitals["Great Britain"]` to get the same result.

Hashes are very convenient if you need to associates two sets of data: countries and capitals, usernames and number of friends, book titles and the number of readers, and so on.

Just like an array, a hash is an object of class Hash, for which you can easily find the documentation by googling "ruby hash" ([try it!](https://www.google.com/?q=ruby%20hash#q=ruby+hash) ). The Hash class also has lots of methods that allow you to query and update the hash. Finally, just like an array, there are two ways to create a new, empty hash:

````ruby
empty_hash = {}
another_empty_hash = Hash.new # same as {}
````

Play with the hash in [IRB](https://blog.makersacademy.com/playing-in-irb-34e5498f7cd5#.1x3texuc4) to learn how to use it. You'll be using hashes and array in every Ruby project you'll ever build.

## Useful methods

Ideally, you will want to learn [all the methods](http://ruby-doc.org/core-2.1.4/Hash.html) for the Hash class. That may seem like a daunting task, so we recommend that you break it down into small, easily digestible chunks. 

Here are a few commonly used methods to get you started:

- [key](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-key)
- [keys](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-keys)
- [has_key?](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-has_key-3F) and [has_value?](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-has_value-3F)
- [invert](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-invert)
- [flatten](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-flatten)
- [to_a](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-to_a)
- [to_s](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-to_s)
- [select](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-select) and its opposite, [reject](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-reject)
- [each](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-each), [each_key](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-each_key), [each_value](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-each_value) and [each_pair](http://ruby-doc.org/core-2.1.4/Hash.html#method-i-each_pair)
