


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

* <i> Callback function is still syncronous(blocks operation). 
* Callback becomes `asyncronous` depending on how I use `callback`. 
* Asyncronous program can do multiple task at the same time. 
* Asyncronous program are `hard to write` & `debug`
* Modern JavaScript `don't` use `callback` function for Asyncronous Program. </i>

#### So let's just not waste time on discovering `how can I use callback to make asyncronous function`.

# Promise

* Modern JavaScript use `promise` to create ASYNCRONOUS function.

<br>
<br>
<br>

<b> 
The foundation of ASYNCRONOUS JAVASCRIPT is "promise".
</b>


<br>
<br>
<br>

* <i> Promise is a `javascript built-in object`.
* Promise return two things.
* One: Returns something if Promise meets certain condition.
* Two : Returns error if Promise doesn't meet certain condition. </i>
* Syntax: 
```javascript
const myPromise = new Promise(); // Basic Syntax
// new Promise() takes an anonymous function. () => { }

const myPromise = new Promise( ( resolve, reject ) => { });
// resolve : when 
```
