


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
// resolve : used for returning "something" on "success".
// reject : used for returning "error" on "failure".

```


```javascript
const myPromise = new Promise( ( resolve, reject ) => {
  if( condition ) {  // if condition is true
    resolve ( );
    // inside this = ( ) whatever we put will be returned by the promise.
  }

  else if ( !condition )  { // if condition is false
    reject ( );
    // if operation is unsuccessful whatever inside of reject() will be returned.
    // this doesn't have to be a error message. Can be anything.
    // But this reject () is used to send Error message.
  }
})
```

```javascript
.then() // it catches the "resolve" value
.catch() // it catches "reject" value

myPromise   // we can put space here for better readibility, never use (;) here.

.then(
  ( resolve ) => {  // .then and .catch takes an anonymous function.
    // that anonoymous function takes an argument that catches the resolve value.
    console.log( resolve );
})

.catch (
  ( err ) => {
    console.log( err );
}) 
```


```javascript
// very basic usuage
let x = 1;

const a = new Promise ( ( resolve, reject ) => {

  const data = {
    // here contains a person data
    firstName: 'john',
    age:20
  }

  if( x === 1 ) {
    // if x value is 1, then promise will return  "data"
    resolve("contains data");
  } else {
    // if x's value not 1 then promise will return "error message"
    reject ( "Error: x is not equal to 1, change x's value to 1" );
  }
})
```

<br>
<br>
<br>

# Questions:
* <i> What is callback?
* Write a basic structure of callback with code.
* Is callback function asyncronous?
* What is `syncronous function`?
* What does modern JavaScript use for asyncronous programming?
* What is Promise?
* What are the two things that Promise return?
* Write basic structure of Promise.
* How to catch the Promise's resolve and reject?
</i>


<br>
<br>
<br>

# Promise within a function 
```javascript
const x = () => {
  return new Promise( ( resolve, reject ) => {
    
  }
}

// technically this x() function bocomes a Promise.
x().then().catch();
```

<br>

Here is a difference between basic Promise and a functional Promise
```javascript
// FUNCTIONAL PROMISE
const x = () => {
  return new Promise( ( resolve, reject ) => { } ) }

x().then().catch();
// if it is a function promise, I have to use (), parenthesis with x
```



```javascript
// BASIC PROMISE
const x = new Promise ( ( resolve, reject ) => { } ) }

x.then().catch();
// if it is a basic promise, then I won't have to use (), parenthesis with x.
```








