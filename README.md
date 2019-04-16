# Reading Values From Hashes

## Learning Goals

- Retrieve data from hashes using its keys and the "bracket" method

## Introduction

Okay, with the basics of hash creation covered, we can now talk about accessing
data from a hash.

In this lesson, we're going to look at how we get values from a hash using
its keys.

## Retrieving Data from Hashes

Retrieving data from a hash is similar to retrieving data from an array, but
instead of giving an array the index number in brackets `[i]` we give a hash the
name of the key `[key]`. If an array is a **list** in which we access index items by
their number, a hash is a **dictionary** in which we access values by their key.

```ruby
pets = {"cat" => "Maru", "dog" => "Pluto"}
#=> {"cat"=>"Maru", "dog"=>"Pluto"}

pets["cat"]
#=> "Maru"
```

Using `[]` is referred to as the **"bracket method".** It is actually a method
just like any other––just like the methods you've been defining and like the
methods available on objects such as Strings.

The bracket method works the same way when using symbols:

```ruby
meals = {:breakfast => "cereal", :lunch => "peanut butter and jelly sandwich", :dinner => "mushroom risotto"}
#=> {:breakfast=>"cereal", :lunch=>"peanut butter and jelly sandwich", :dinner=>"mushroom risotto"}

meals[:breakfast]
#=> "cereal"
```

It will also work if we use integers for keys. However, it is important to
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

## Receiving `nil` When No Key is Found

If we use the bracket method and pass in a value that does not match a key on
the hash, Ruby will return `nil`:

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

## Conclusion

Given a hash and its keys, we can retrieve all the values present in that hash.
We are now able to create hashes as a way to store associated data and can use
the bracket method to retrieve that stored data as needed.
