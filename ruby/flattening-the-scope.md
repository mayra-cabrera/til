Scopes acts as gates, like formidable barriers. As soon as we walk through one of them local variables fall out of scope.. right? Well in metaprogramming this can be a little different. Iit turns out that if you replace scope with method calls, **you allow one scope to see variables from another scope**. In english, this means that two scopes can share variables if the scopes are "squeezed" together. See the following example

````
my_name = "Mayra"

class HappyClass

  def my_happy_method
  end

end
````

I want to print `my_name` var inside `HappyClass` and inside `my_happy_method`, how do I do it? Lets start with the class, we can replace `class` with something else: a method call. If we could call a method instead of using the `class`keyword, we could capture `my_name` in a closure and pass that closure to the method. Yup, I'm talking about `Class.new`, so

````
my_name = "Mayra"

MyClass = Class.new do

  puts "#{my_name}"

  def my_method
  end
end
````

Now how can we use `my_name` inside `my_method`, once again we need to replace the keyword with a method call, so

````
my_name = "Mayra"

MyClass = Class.new do
  puts "#{my_name}"

  define_method :my_method do 
    puts "#{my_name}"
  end
end
```
