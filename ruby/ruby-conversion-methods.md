# Ruby conversion method

The most commonly used `to_` method is probably `to_s`. Every Ruby object, except
instances of BasicObject, responds to `to_s`, and thus has a way of displaying itself as
a string.

```ruby
> "Supercalifragilistico!".to_s
=> "Supercalifragilistico!"
> 1.to_s
=> "1"
```

If you use `to_s` within an object, you'll received a kind of cryptive & descriptive message:

```ruby
> Object.new.to_s
=> "#<Object:0x000001030389b0>" # Usual class and memory-location screen dump
```

Ruby displays the same thing when you use `puts` within an object

```ruby
> puts Object.new
=> "#<Object:0x000001030389b0>"
```


What you might not know is that by overriding `to_s` method it will surface up to `puts` definition

```ruby
> obj = Object.new
=> #<Object:0x000001011c9ce0>
> puts obj
#<Object:0x000001011c9ce0>
=> nil
> def obj.to_s
 "Well hello there :D"
end
> puts obj
=> Well hello there :D
```

And the same thing will happen using the string interpolation

```ruby
> "My object says: #{obj}"
=> "Well hello there :D"
```

Also notice that if an object responds to `to_str, its `to_str` representation will be used when the object is used as the argument to `String#`. Here's an example involving a simple `Person` class:

```ruby
class Person
  attr_accesor :name
  def to_str
    name
  end
end
```

If you create a `Person` object and add it to string, `to_str` kicks in with the `name`string:

```ruby
> mayra = Mayra.new
> mayra.name = "Mayra"
> puts "mayra is named: " + mayra
=> "mayra is named: Mayra"
```

But wait there's also more, you can do this with arrays if you override `to_ary` method:

```ruby
class Person
  attr_accesor :name, :age, :email
  
  def to_ary
    [name, age, email]
  end
end


> mayra = Mayra.new
> mayra.name = "Mayra"
> mayra.age = 100
> mayra.email = "mayra@fakeemail.com"
> array = []
> array.concat(mayra)
> puts array
["Mayra", 100, "mayra@fakeemail.com"]
```

