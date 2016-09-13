### Functions as values

It turns out that functions are just values, so we can pass one function as a function value. So this code: 

```javascript
function logEach(array) {
  for (var i = 0; i < array.length; i++)
    console.log(array[i]);
}
```

Can be re-written like this



```javascript
function forEach(array, action) {
  for (var i = 0; i < array.length; i++)
    action(array[i]);
}

forEach(["Wampeter", "Foma", "Granfalloon"], console.log);
```

Or even you can create a function on the spot:

```javascript
var numbers = [1, 2, 3, 4, 5], sum = 0;
forEach(numbers, function(number) {
  sum += number;
});
console.log(sum);
```

