


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

y(x) // calling x function in y function as argument.
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

<br>
<br>
<br>


# Practical
Goal: 
* The goal is to create a Promise that takes a password
* If the password is correct then `a data object` will be <b>promised </b>
* If the password is incorrect then it will return `an error`.

```javascript
const x = (password) => {

    // creating an object which will return if password is correct
    const a = {
      firstName: "john",
      age: 20
    };

    // for creating functional Promise, I have to return a basic promise
    return new Promise( (resolve, reject ) => {
        if(password === "helloworld") {
            resolve(a);
        }
        else {
            reject(`Error: The password is wrong`);
        }
    })
}


x("helloworld")  // calling the functional promise and giving password as argument.

.then( ( res ) => {  // if the password is correct, then() will print the object 
    console.log(res);
})

.catch( ( err ) => {  // incorrect password will print the error
    console.log(err);
} )
```


<br>
<br>
<br>
<br>

# async/await
* `async` keyword is more fashionable way to create `promise`.
* Coders can only use `async` before a function.
* `async/await` is simply <b>Cleaner and Easier way </i> to write `promise`. </b>

<br>
* Basic Syntax: 

```javascript
const getData = async () => { } // arrow functions , also function expression

const getData = async function () { }  // function expression

async function getData () { } // function declaration
```

<br>

Behaviour of `async` function
```javascript
const x = async () =>{
    for(let i =0; i < 100000000; i++) {
        if( i == 10000000) {
            return ( i );
        }
    }
}

x().then( (res ) => {
    console.log(res);
})

console.log("hello world");


//output:
//hello world
//10000000
```
> Even if i called the x() before hello world console for its async functionalities, x() result was logged in console after printing hello world

<br>

Now I know that Promise returns two things. <br>
One is the `resolve`. <br>
Another One is the `reject`. <br>
How can I specify resolve and reject here?

<br>
<br>

This is where the topic gets complicated. <br>
<i> There are so many <b>combination</b> to do in `async function`. </i>

<br>
<br>


Doing Basic Promise resolve()
```javascript
const x = async () => {
  // do some processing

  // this is One FORM of resolving
  // simply return something.
  // That value(returned) will be catched by .then ()
  return "hello world"
}

x().then( (result) => {
  console.log(result); // output : hello world
})
```

<br>

Note: There are some code that contains `Promise.resolve()` in async function on the website documents. `Don't follow that code`.
```javascript
const x = async () => {
  Promise.resolve("hello world");
  // DO NOT use Promise.resolve() here.
}

x().then( (result) => {
  console.log(result); // output : hello world
})
```

#### Do not use Promise.resolve() in `async function()`

<br>
<br>


* What I've learned so far:
* <i> `async` keyword can be used before function `const x = async () => {}`
* Create an `async function`
* Whatever gets `returned`, is the `resolve` of the hidden `promise`.
</i>

<br>

There are two things I can do in `async function`
* Await 
* try{ }  catch() { }

<br>
<br>
<br>

# await
* What exactly `await` is?
* `await` does a lot of things.
* `await` <b>pause</b> next line execution within `async function`, untill await complete its task.
* It doesn't pause code outside of the `async` function.
* `await` can only be used within `async function`.

<br>

* This information is complex to understand. <b>FOCUS</b>.
* `async function` can resolve its hidden promise by `return` something. That can be catched by ` function().then( () => {} )`
* One: `async` function can create Promise.
* Two: `async function` can very easily <b>unwrap</b> other promise's `resolve`, using `await`.
* So `await` does two things. 1) Pause the next line execution... 2) Unwrap other promises `resolve`.

<b>Question</b>: when should we use await? <br>

<br>
<br>

Let's just write am `async` function which gets a promise's resolve, using `await`.
```javascript
// Goal : to know if await can unwrap other promise's resolve 
// and immidiately store it in variable

const x =2;

const z = new Promise( (resolve, reject ) => {
    //created a new promise 
    // this will return resolve
    if (x ===1 ) {
        resolve("this is resolve");
    }
    else{
        reject("Error: x's value should be one.")
    }
})


// lets create async function that will use await to unwrap the promise's resolve
const a = async () => {
    let t = await z;
    // await unwrap the promise's resolve
    // which I can use, store in a variable.
    // also await pause execution of next line code untill it gets "z" resolve.

    console.log(t);
}

a();

//output:
//this is resolve
```



<br>
<br>

## Conclusion: await
So, when should I use `await`? 
* <b>Important:</b> When I need to fetch other `promise`'s resolve.
* <b>Not important:</b> When I need to stop next line code execution untill this task is finished.








