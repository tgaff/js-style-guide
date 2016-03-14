# Javascript style-guide



<a name="use-spaces-around-arguments"></a>
Use spaces around the arguments to a function and the function parameters.
<sup>[[link](#use-spaces-around-arguments)]</sup>


## CSS

#### Use two-spaces for indentation

```css
/* avoid tabs */
.ridiculously-huge {
	font-size: 100
}

/* recommended */
.ridiculously-huge {
  font-size: 100
}
```

## Introductory JS

<a name="use-triple-equals"></a>
#### Choose `===` and `!==` over `==` and `!=`. <sup>[[link](#use-triple-equals)]</sup>



<a name="use-spaces-around-arguments"></a>
#### Use spaces around the arguments to a function and the function parameters. <sup>[[link](#use-spaces-around-arguments)]</sup>

```js
// avoid
console.log("<--- no space there, or here -->");

function doMagic(a, b) { }
```

```js
// recommended
console.log( "<-- space to the left and the right -->" );

function doMagic( a, b );
```


#### Use braces around any multi-line blocks.

```js
// avoid
if (test)
  return false;

// recommended - single line
if (test) return false;

// recommended - multi-line
if (test) {
  return false;
}
```

#### Use literal array syntax for array creation

```js
// avoid
var stuff = new Array();

// recommended
var items = [];
```

#### Use array.push rather than index access 

```js
// avoid
someStuff[someStuff.length] = 'new todo';

// recommended
someStuff.push('new todo');
```

#### When returning multiple values use object destructuring, not arrays 

* It's safer if the return values are ever extended.
* Avoids mistakes in handling return value order.

```js
// avoid
function processInput(input) {
  // ...
  return [strangeness, spin, charm];
}

// recommended
function processInput(input) {
  // ...
  return { strangeness: strangeness,
           spin: spin,
           charm: charm };
}
```

#### Limit lines to around 100 characters and use multi-line String concatenation with +

Strings that cause the line to exceed ~100 characters should be concatenated across multiple lines.

```js
// avoid
var html = '<ol><li>Of shoes</li><li>and ships</li><li>and sealing-wax</li><li>Of cabbages</li><li>and kings</li></ol>'; // Lewis Carroll

// less bad
var html = '<ol>
              <li>Of shoes</li> \
              <li>and ships</li> \
              <li>and sealing-wax</li>\ 
              <li>Of cabbages</li>
              <li>and kings</li> \
              </ol>'; // Lewis Carroll


// recommended
var html = '<ol>' + 
              '<li>Of shoes</li>' +
              '<li>and ships</li>' + 
              '<li>and sealing-wax</li>' +
              '<li>Of cabbages</li>' + 
              '<li>and kings</li>' +
            '</ol>'; // Lewis Carroll
```


### Whitespace

#### Use soft tabs set to 2 spaces.

#### Use one-space before a leading brace.
```js
// avoid
function yay(){
  console.log('yay');
}

// recommended
function yay() {
  console.log('yay');
}
```

#### Place 1 space before the opening parenthesis in control statements (if, while etc.). 

```js
// avoid
if(x === y) {
  return x;
}

// recommended
if (x === y) {
  return x;
}
```

#### Use spaces around operators

```js
// avoid
a=b+c-(d/2);

// recommended
a = b + c - (d / 2);
```

#### Place no space between the argument list and the function name in function calls and declarations.

```js
// avoid
function addNumbers( a, b ) { ... }

// recommended 
function addNumbers(a,b) { ... }
```

function calls:

```js
// avoid 
var addedNumbers = addNumbers( 1, x );

// recommended 
var addedNumbers = addNumbers(1, x);
```

##### When using anonymous functions a space is OK

```js
// OK
var saute = function () { ... };

// also OK
var saute = function() { ... };
```

#### Use one space after a comment marker and indent multiple lines

```js
// avoid
//my comment with no space

// avoid
/* This is a comment that doesn't
use indentation when continuing a sentence. */

// recommended
// my comment with a space

/* This is a comment that does
     use indentation when continuing a sentence. */
```


#### Use leading-dots and indentation when making long method chains. 

```js
// avoid
$('#items').
  find('.selected').
    highlight().
    end().
  find('.open').
    updateCount();

// recommended
$('#items')
  .find('.selected')
    .highlight()
    .end()
  .find('.open')
    .updateCount();

```

> Example lifted from airbnb style-guide.







### Functions

#### Prefer named functions over anonymous functions 

> This rule is particularly important in the first 2-3 weeks of the course.  However, we should eventually introduce anonymous functions.

```js
// avoid
$.get(url).success(function(result) {
  console.log(result);
});

// recommended
$.get(url).success(handleIndexResult(result));

// sometimes OK
$.get(url).success(function handleIndexResult(result) {
  console.log(result);
});

```

#### Use function declarations instead of function expressions. jscs: requireFunctionDeclarations

* Function declarations are fully hoisted.

```js
// bad
var boilPasta = function () {
};

// recommended
function boilPasta() {
}
```

#### Never declare a function in a non-function block (if, while, etc). Assign the function to a variable instead. 


#### Never name a parameter `arguments`. 

* It overrides the arguments object the function receives.

// avoid
function nope(name, options, arguments) {
  // ...stuff...
}

// recommended
function yup(name, options, args) {
  // ...stuff...
}

> lifted from airbnb

## jQuery





## File Organization