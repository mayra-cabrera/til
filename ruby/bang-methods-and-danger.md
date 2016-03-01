# Bang(!) methods and danger 

Ruby methods can end with an exclamation point. The bang has no significance to Ruby internally, bang methods are called and executed just like any other method. But by convention, the bang labes a method as *dangerous*, and that can mean whatever the person writing the method wants it to mean (*If "danger" is too melodramatic for you, you can think of the `!` in method names as a kind of "Hey heads up!".*)

But Ruby really doesn't care, Ruby is happy to execute methods whose names end in `!` whether they're dangerous, safe, paired with a nonbang method, not paired - whatever. The value of `!` notation as a token of communication between a method author and a user of that method resides entirely in conventions. So here's a list of advices on when to use bang-terminated method names:

* **Don't use ! except in M/M! method pairs**. The `!`notation for a method name shoyld only be used when there's a method of the same name without the `!`, when the relation between those two methods is that they both do substantially the same thing, and when the bang version also has side effects 
* **Don't use ! just becase you think your method is dangerous in some vague way**. All methods do soemthing, that in itself isn't dangerous. The `!`is a warning that there may be more going on that the name suggest. 
* Always remember **the bang doesn't mean destructive, it means dangerous, possibly unexpected behaviour** 
* **Destructive methods do not aways end with `!`**. Many nonbangs methods have name that lead you to expect the receiver change, but you'll almost certainly find that the convetional usage of the `!` notation is the most elegant and logical usage. 
