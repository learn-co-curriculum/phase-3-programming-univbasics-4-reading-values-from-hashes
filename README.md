# Reading Values From Hashes

## Learning Goals

- Retrieve data from hashes
- Handle a `nil` response when no key is found

## Introduction

In this lesson, we're going to look at how we get values from a hash using
its keys. If an array is a **list** in which we access index items by
their number, a hash is a **dictionary** in which we access values by their key.

## Retrieving Data from Hashes

Retrieving data from a hash is similar to retrieving data from an array, but
instead of giving an array the index number in brackets `[i]` we give a hash the
name of the key `[key]`. The Hash will return the value associated with the
_key_.

```ruby
pets = {"cat" => "Maru", "dog" => "Pluto"}
#=> {"cat"=>"Maru", "dog"=>"Pluto"}

pets["cat"]
#=> "Maru"
```

Using `[]` is referred to as **"bracket notation".**

Keep in mind, _keys_ can be `Symbol`s instead of `String`s. The `Hash` lookup works
just the same:

```ruby
meals = {:breakfast => "cereal", :lunch => "peanut butter and jelly sandwich", :dinner => "mushroom risotto"}
#=> {:breakfast=>"cereal", :lunch=>"peanut butter and jelly sandwich", :dinner=>"mushroom risotto"}

meals[:breakfast]
#=> "cereal"
```

It will _also_ work if we use `Integer`s for keys. It is important to
remember that when using the bracket method on a hash, Ruby is not looking for
the index like it would in an array. Instead, Ruby is looking for the key that
matches whatever is inside the brackets and returns the associated value:

```ruby
healthy_things = {1 => "learn to garden", 2 => "plant seeds", 10 => "eat vegetables"}

healthy_things[10]
#=> "eat vegetables"
```

We can also use variables inside the brackets:

```ruby
key = :name
#=> :name

user_info = {:name => "Ada", :email => "ada.lovelace@famous_computer_inventors.com"}
#=> {:name=>"Ada", :email=>"ada.lovelace@famous_computer_inventors.com"}

user_info[key]
#=> "Ada"
```

## Handle a `nil` Response When No Key Is Found

If we use the bracket notation and pass in a value that does not match a key on
the hash, Ruby will return `nil` by default:

```ruby
grocery_items = {:apples => 10, :pears => 4, :peaches => 2, :plums => 13}
#=> {:apples=>10, :pears=>4, :peaches=>2, :plums=>13}

grocery_items[:rambutans]
#=> nil
```

This turns out to be very useful. Remember that in Ruby, `nil` is _falsy_ while
**any data type value** is _truthy_ (even empty arrays and hashes). This
behavior allows us to easily check if a hash has a key/value pair or not as we
can use the bracket method in a conditional statement:

```ruby
grocery_items = {:apples => 10, :pears => 4, :peaches => 2, :plums => 13}
#=> {:apples=>10, :pears=>4, :peaches=>2, :plums=>13}

if grocery_items[:rambutan]
  puts "Rambutan present!"
else
  puts "No rambutan."
end
# No rambutan.
```

> **STRETCH**: Look at the documentation for the `Hash` class. See if you
> can find a method that will look up a _key_ and will let you specify
> what to return if the _key_ is not found! The default data types of
> Ruby have POWERFUL magic inside of them that's yours to discover. As a hint
> it's a method that a dog ight know to respond to :)

## Conclusion

Given a hash and its keys, we can retrieve all the values present in that hash.
We are now able to create hashes as a way to store associated data and can use
the bracket method to retrieve that stored data as needed.
