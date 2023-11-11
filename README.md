


# Goal
* Main goal of `Asyncronous JavaScript` is to not block other code in the program.


<br>
<br>

# Callback
* When a functions is called in another function `as argument`.

```javascript
const x = ( ) => {
  // first function
}

const y = ( callback ) => {  // added an argument that takes function.
  // this function is called as an argument.
  callback();
}
```

<br>

> now I know what is callback.

* <i> Callback function is still syncronous(blocks operation). </i>
* <i> Callback becomes `asyncronous` depending on how I use `callback`. </i>
