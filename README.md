# Symbols, Arrays and Collections
#### by Francke Jones
francke.jones@gmail.com

## Objectives

Confidently be able to recognize and work with the following objects:

+ Symbols
+ Arrays
+ Hashes
+ Sets Introduction

## What are Symbols?

Earlier, we learned the concept of a string, and why computers need data-types to process information. Symbols are considered a data-type like strings, only they posess a different set of attributes. For one, they are immutable - there is no such thing as appending characters to a symbol or changing a symbols object. They cannot be altered.

Symbols are a lot like strings. ```"apple"``` and ```:apple``` behave similarly; for example, both can be used as keys in a hash. 

Symbols are globally unique. This means that they're always the same everywhere in your app. (They're like global keys.)

The string value of a symbol is the string part after the colon (so, ```:apple``` as a string is ```"apple"```). But, symbols aren't true strings. (They're objects.)

Let's compare strings and symbols by looking at their object states:

    "abc".object_id
    "abc".object_id
    :abc.object_id
    :abc.object_id

Internally, Ruby uses symbols to keep track of all the names it's created for variables, methods and constants. You can see a list of them using the ```Symbol.all_symbols``` class method.

## Symbols as Hash Keys

Soon we'll be talking about hashes. Before we do, know that Symbols are commonly used as Hash keys - there are a few advantages of using hash-keys. 

1. First, Ruby can process symbols faster, so if your doing a lot of lookups, uses symbols
2. Symbols look good as has keys. They look frozen, Ruby users tend to use them a lot.
3. In Ruby 2.0, a common pattern for writing hashes looks like:
	
	```hash = { name: David, age: 49 }```

    ```hash = { :name => "David", :age => 49 }```
    
    
    
## Symbols and strings in comparison

Symbols have learned to do a lot of things from the string domain. Let's have a look at some of those methods. 

    Symbol.instance_methods(false).sort
    
But, there are no bang versions of these methods

# Arrays!

- Sequentially ordered collections with arrays
- Keyed collections with hashes

## What is an array?

In programming in general, you deal not only with individual objects but with collections of objects. You search through collections to find an object that matches certain critera.

- Cheat sheet: Array.instance_methods

In ruby, there are two built in core classes that handle the bulk of these operations. Arrays and Hashes!

First, let's look at an array:

    array = ["ruby", "diamond", "emerald"]
    puts array [0]

There are several ways to create a new array

    a = Array.new
    Array.new(3)
    Array.new(3, "abc")

You can supply a codeblock to an array:

    n = 0
    Array.new(3) { n+=1; n*10 }

Inserting, retriving, and removing array elements with the - 

Set Method:

    a = []
    a[0] = "first"
    
Get Method:

    a = [1, 2, 3, 4, 5]
    p a[2]
    
Setting or Getting Multiple Elements:

    a = ["red", "orange", "yellow", "purple", "gray", "indigo", "violet"]
    a[3,2]
    a[3,2] = "green", "blue"
    a
    
Manipulating arrays with unshift & push / shift & pop:

    a = [1, 2, 3, 4]
    a.unshift(0)
    b = [1, 2, 3, 4]
    b.push(5)
    b.push(6, 7, 8)
    c = [1, 2, 3, 4, 5]
    c
    popped = c.pop
    puts popped
    shifted = c.shift
    puts shifted

    
Combining arrays with other arrays:

    d = [1,2,3].concat([4,5,6])
    d = []
    d = [1,2,3]
    f = d + [4,5,6]
    
Can anyone guess how to remove duplicates? Look through the documentation...

    d = [1, 2, 3, 3, 4, 5, 6, 7]
    d.count(item)
    d.uniq
    
Additional Methods

    d.size
    d.empty


# Hashes!

Like an array, a hash is a colleciton of objects. A hash consists of key/value pairs where any key and any value can be any Ruby object. Hashes let you perform lookups based on keys. In addition to simple keybased value retrieval, you can also perform more complex filtering and selection operations. 

- Cheat sheet: Hash.instance_methods

A typical example would be a list of states with their abbreviations:

    state_hash = {"Conneticut" => "CT", "Delaware" => "DE", "New Jersey" => "NJ", "Virginia" => "VA"}
    state_hash = { CT: "Conneticut", DE: "Deleware", NJ: "Deleware", VA: "Virginia" }
    
Retrieving values from a hash:

    conn_longform = state_hash.fetch(:CT)
    
Adding a Key/Value pair to a Hash:

    h = Hash.new
    h["a"] = 1
    h["a"] = 2
    puts h["a"]
    
Replacing contents and clearing a Hash:

    stat_hash = {first: "foo", second: "bar"}
    stat_hash.replace({new_first: "foo2", new_second: "bar2"})
    state_hash.clear
    
Examples in rails apps and common uses of Hashes in apps:

    link_to "Click Here", :controller => "work", :action => "show", :id => work.id
    
    
More hash methods: 

    h.has_key?(1)
    h.has_value?("three")
    h.empty?
    h.size
    



