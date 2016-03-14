# Stricter conversions with integer and float
*This is based on The Well Grounded Rubyiest book, you should definitly buy it*

As a ruby programmer you probably have experimented with converting strings to integers, and ruby has some secret under their slive with this conversion:

```ruby
"hello".to_i
=> 0
"123hello".to_i
=> 123
```

As you can see if your string has no reasonable integer equivalent ("hello") ruby `to_i` method will always return 0. Otherwise if your string starts with digit but isn't made up entirly of digits ("123hello"), the nondigit parts are ignored and the conversion is perfomed only on the leading digits. The same thing happen with `to_f` method:

```ruby
"hello".to_f
=> 0.0
"1.23hello".to_f
=> 1.23
```

Sweet huh? But the conversion methods arent a bit flexible? What about if I want to avoid those kind of things? Well lucky for you, Ruby has a couple of stricter conversion techniques: `Integer` and `Float`

```ruby
"123abc".to_i
=> "123"
Integer("123abc")
=> ArgumentError: invalid value for Integer(): "123abc"
Float("3")
=> 3.0
Float("-3")
=> -3.0
Float("-3xyz")
ArgumentError: invalid value for Float(): "-3xyz"
```

So if you want to be strict about what gets converted and what gets rejected, `Integer` and `Float` can help you on :)

