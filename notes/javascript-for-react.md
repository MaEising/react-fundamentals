# JavaScript for React

_based on this https://kentcdodds.com/blog/javascript-to-know-for-react_

## Closures

A closure gives access to an outer function's scope from an inner function.
Closures are created every time a function is created.

### Lexical Scoping

If functions are nested, the inner function `displayName()` is able to access
the local variable `name` in the outer function `init()`.

```js
function init() {
  var name = 'Mozilla' // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, a closure
    alert(name) // use variable declared in the parent function
  }
  displayName()
}
init()
```

### Closure

```js
function makeAdder(x) {
  return function (y) {
    return x + y
  }
}

var add5 = makeAdder(5)
var add10 = makeAdder(10)

console.log(add5(2)) // 7
console.log(add10(2)) // 12
```

This is because functions in JavaScript form closures. A Closure is the
combination of a function and the lexical environment within which that function
was declared. This environment contains any local variables that were in-scope.
In essence, makeAdder is a function factory. It creates functions that can add a
specific value to their argument. In this example, two new funcions are created,
stored in `add5` and `add10`. `add5` adds five to its argument, and `add10`
adds 10. `add5` and `add10` are both closures.
