### Using fetch to assert o default keys

*Taken from Confident Ruby*

There are some situation in which certain hash keys are required for correct operation. Instead of validating this precondtion we can use fetch to retrieve the required attributes, making our preconditions far more concise

Rather than the following:

    def add_user(attributes)
      login = attributes[:login]
      unless login 
        raise ArgumentError, "Login must be supplied"
      end
      password = attributes[:password]
      unless password
        raise ArgumentError, "Password must be supplied"
      end
      ...
    end

We can use this:

    def add_user(attributes)
      login = attributes.fetch(:login)
      password = attributes.fetch(:login)
      ...
    end

What difference does it make? It we call add_user without the required attributes a `KeyError` exception is thrown:

    add_user {login: "kittie"}
    => #<KeyError: key not found: :password>

We can also use fetch to default some key:

    h = { "a" => 100, "b" => 200 }
    h.fetch("a")                            #=> 100
    h.fetch("z", "go fish")                 #=> "go fish"

Because fetch only executes and returns the value of the given block if the specified key is missing, so is like saying "here is the default value"