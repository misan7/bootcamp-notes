# HTML Tips
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    div>ul>li{item $}*10  <!-- Tab to develope  -->
</body>
</html>
```

# JAVASCRIPT

Aporta dinamismo a las páginas web


## Web development in 3 capes

**Content**: html gives the structure base to show the basic elements. www are pages vinculated between them.

**Design**: css give the style to the page. Make it look better. The content is the same.

**Behaviour**: javascript do the actions that the page do, open windows, loops... 
- is an interpreted language, not a compilated language. 
- The browser can read the cape without compilation.
- *ECMAScript*: specification language.

```
ECMAScript 3 -> Past
ECMAScript 5 -> Present
ECMAScript2015 or ES6 -> Future
```

**AJAX**: example Gmail, different operations at same time: navigate, write an email...

Every _browser_ have a different _engage_ for decide how to execute JavaScript. And for this reason some browsers are faster than others.

**jQuery** helps to manage different browsers compatibilities.

###Types of variables:
- Number: 5
- Strings: "sergio"
- Boolean: true
- Undefined
- Null

###***If is not a type of variable is an object.***

```
var a = 1

var b

var b =10

key sensitive: use of mayus or minus makes difference:

var NamE != var name != var NaMe
```

**type of**:
```
var a = 4

type of a
"number"

var b = "sergio"

type of b
"string"

var c = true

type of c
"boolean"
```

**NaN**:
```
var a = 4
var c = 4/"sergio"

c
NaN (Not a Number)
```

**Operators**:
+ Addition

- Substraction

* Multiplication

/ Division

% Modulo: 

```
var c = 3 + 4 + "10" + 4

c = "7104"

type of c

"string"
```

**++ Increment**:
```
var a = 5
++a
a = 6
```

```
var a = 5
var b = a++
b = 5
a = 6
```

```
var a  = 5
var b = ++a
b = 6
a = 6
```

INSERT HERE && AND ||-----------------------------------------------------------

## Comparison operators:
_Compare values and return true or false._

== Equality
```
2 == 2
true
2 == "2"
true
```
=== Equality and type (compare value and type)
```
2 === 2
true
2 === "2"
```
!= Non equality
```
2 != 2
false
2 != 3
true
```
!== Non-equality without type conversion
```
!==
2 !== 2
false
2 !== "2"
true
```

## Conversions
```
var a = 5
type of a = "number"
```
```
var a = a + "3"
type of a = "string"
```
```
var s = "100"
var s = s * 1
type of s = "number"
```
```
var a = "2342342523523"
var b = (+a)
b = 2342342523523
type of b = "number"
```

**Double negation** `!!` converts into its boolean
All converts to true except these:
```
""
null
undefined
0
NaN
false
```

Example:
```
!!(true && 5 && "")
false
```


##Conditional states

**if... else**:

The first `if` excludes the next `else if` and `else`

**Ternary Operator**:
```
var result = ( a === 1 ) ? "is one" : "is NOT one!!"

if a is equal 1 result = "is one", else result = "is NOT one!!"
```

**switch**:

Is used when there 3 or 4 cases. The `break` ends the function.


##Loop

**while**
```
var i = 0

while ( i < 10 ) {
    console.log(i)
    i++;
}
```

**do while**
```
var i = 10

do {
    console.log(' i is ' + i)
    i++
} while ( i < 10 )
```

**for**
```
var punishment = '';

for (var i = 0; i > 100; i++) {
    punishment += "I will not do it again"
}
```

```

for ( _initialization_ ; _evaluation_ ; _increment_ ) {

}
```

_Example of multiplication's tables_:
```
var res= ' \n';
for (var i=1; i<=10; i++) {
    for (var j=1; j<=10; j++) {
        res += i*j + '\t';
    }
    res += '\n';
}
```
The console shows:
```
" 
1   2   3   4   5   6   7   8   9   10  
2   4   6   8   10  12  14  16  18  20  
3   6   9   12  15  18  21  24  27  30  
4   8   12  16  20  24  28  32  36  40  
5   10  15  20  25  30  35  40  45  50  
6   12  18  24  30  36  42  48  54  60  
7   14  21  28  35  42  49  56  63  70  
8   16  24  32  40  48  56  64  72  80  
9   18  27  36  45  54  63  72  81  90  
10  20  30  40  50  60  70  80  90  100 
"
```


##Functions
```
function sum(a, b) {
    var c = a + b
    return c
}
```

A `function` always give a value. Just **ONE** value.
A `function` is called by its name and values (Example: `sum(2, 6)`)
without `return` it returns `undefined`.

`arguments` is a **pseudo-array**:
```
function sum() {
    for (var i = 0; i<arguments.length; i++) {
    sum += arguments[i]
    }
    return sum;
}
```

**How to change base with parseInt:**
```
parseInt(FF, 16) -> Converts the first part in base 16 (Hexadecimal)
Hexadecimal:    0 1 2 3 4 5 6 7 8 9
                A B C D E F
```

```
rgb (255, 255, 255) -> White
rgb (0, 0, 0) -> Black
#FFFFFF -> White
#000000 -> Black
```

```
FF (hexadecimal) => 255 (decimal)
15*1 + 15*16 // 255
parseInt("FF",16) // 255
```




## FUNCTIONS

Difference from junior to senior.

**Functions Scope**:

This functions have the same value
```
function f() { return 3;}       FUNCTION NOMINAL
var f = function() {return 3;}  FUNNCTION ANONYMOUS
```

```
function sum(a,b) { return a+b }
sum(2,4)

var sum = function(a,b) { return a+b; }
sum(2,4)
```

```
type of sum // "function"
```

 
###Callback Function

Inside of function b() its called the mother function a()
f is `callback function` of _doSomething_:

```
function doSomething(x,y) {
    return f(x)
}
```

###Closures

The **visibility** of the functions are **local** and can see the values of the _father function_ and _global_. But the children function n() can't be seen from out:

```
function f() {
    var b = 2
    function n() {
        var c = 2
    }
}
```


###Lexical Scope

Functions create the **mark of scope** when they are _defined_, not when they are _executed_.

```
function f1(){ var a = 1; return f2(); }

function f2() { return a; }

f1() // undefined
```


```
var a = 10

function f1(){ var a = 1; return f2(); }

function f2() { return a; }

f1() // 10
```

**Scope Chain**
A `function` has the _visibility_ from its `father function`.

**Hoisting**:
Is a good practise to declare `vars` in the first lines to use the `hoisting` effect.
```
var a =123

function f(){
    alert(a)    // Undefined
    var a = 1
    alert(a)    // 1
}

f()
```

**Closure**

```
function f(arg) {
    var n = function() {
    return arg;
}
arg++
return n
}

var m = f(123)
m()             // 124
```

```
function timesCallFn(){
    var times = 1
    return function() {
        return times++  // Return actual value and increment after
    }
}

var m = timesCallFn()
m()                     // 1
m()                     // 2
m()                     // 3
```



##Array

An `array` is a list of values.
```
var beatles = ['John', 'Paul', 'George', 'Ringo']
beatles[0] = 'John'

var myArray = [3, 'Juanma', true, function()]
myArray.push = 34                       // [3, 'Juanma', true, function(), 34]
myArray[myArray.length] = 34            // [3, 'Juanma', true, function(), 34]
```




##Object

```
var hero = {
    breed: 'Turtle',
    occupation: 'Ninja'
}
```

How to **acces** into a **property**:
```
hero.breed          // 'Turtle'
hero['occupation']    // 'Ninja'

var myProp = 'breed'
hero[myProp]        // 'Turtle'
```

```
var boss = {
    name: 'julian',
    age: 54,
    isBoss: true,
    employees: ['Paco', 'Maria', 'Pepe']
    double: function(x) {return x*2}
}
```

When a **property** contain a `function`, this property is a `method`.
A `method` is a **property** of an **object**.

```
var book = {
    name: 'Catch-22',
    author: {
        firstname: 'Joseph',
        lastname: 'Heller',
    }
}
```

Calling a **property**...
```
book.author.firstname       // 'Joseph'
book[author].firstname      // 'Joseph'
book.author[firstname]      // 'Joseph'
book[author][firstname]     // 'Joseph'
```

## Exercises

```
var x = 'Hello World';
function foo(){
    var x;
    alert( x );
    x = 'New Value';
    alert( x );
}
foo();
```

1st alert will show `undefined`
2nd alert will show `New Value`

```
function test() {
    foo();
    bar();
    var foo = function () {
        alert("this won't run!");
    }
    function bar() {
        alert("this will run!");
    }
}
test();
```

The first `function foo` will not start. Just the `function bar` because it has content. If its written `foo()` after, it will work.

```
var mathy = function(x) {
    return function (y) {
        return function (z) {
            return (x / y) - z;
        }
    }
}
¿Cómo hariamos la operación (4 / 3) - 2 con este código en una linea?
```

The solution is:
```
var mathy(4)(3)(2)
```

**closure**
```
var superGreeter = function(greeting) {
    return function(place) {
        return function(nickname) {
            return function(name) {
                return greeting + ', ' + name + '! Welcome to ' + place + ', ' + nickname + '.';
            }
        }
    } 
};
­
superGreeter('Hey')('Berlin')('old pal')('Hans')
//'Hey, Hans! Welcome to Berlin, old pal.'
­
hiParisBuddyGreeter = superGreeter('Hi')('Paris')('buddy');
helloTokyoGreeter = superGreeter('Hello')('Tokyo');
­
hiParisBuddyGreeter('Franz')
//'Hi, Franz! Welcome to Paris, buddy.'
helloTokyoGreeter('friend')
//[Function]
helloTokyoGreeter('friend')('Yuki')
//'Hello, Yuki! Welcome to Tokyo, friend.'
```

##this

`this` adquires the value when is executed. `This` used inside the method of an object, represents the object.

```
var hero = {
    name: 'Raphael',
    sayName: function() {
        return this.name;
    }
}

hero.sayName()      // 'Raphael'
```



## Constructor Function

## mETHODS
https://github.com/juanmaguitar/javascript-notes/tree/master/markdown-en/06-global-objects/arrays#basic-methods-of-array

Take notes about indexOf( "word", 2)
function sort for numbers


## Higher Order functions

### for.each() == Function that uses another function

for.each return nothing, just operates.

```
var beatles = ["John", "Paul", "George", "Ringo"]

beatles.forEach( function(item) {
    console.log(item.toUpperCase()) })
JOHN
PAUL
GEORGE
RINGO
```

```
beatles.forEach( function(item, index) {
    console.log(index + " " + item.toUpperCase()) })
0 JOHN
1 PAUL
2 GEORGE
3 RINGO
```

**item** = value, use the semantic name, for example "beatleName".
**index** = position in the array, use the semantic name, for example "bandPosition"

```
var myNumbers = [2, 6, 34, 12]

var doubledNumbers = []

myNumbers.forEach( function(item) { doubledNumbers.push(item*2) })
var myDoubledNumbers        // [4, 12, 64, 24]
```

### map()

Return an array

```
var myDoubledNumbers = myNumbers.map( function(item) { return item*2 })

var myDoubledNumbers        // [4, 12, 64, 24]
```

## filter()

Just the numbers `> 5`
Return an array

```
[1,3,2,5,2,4,3,5,4,35,3].filter( function(item) { return item > 5 })
```

## every() = all; some() = one

true or false if all elements follow a determinated function
Returns a boolea.

```
[2,4,5,2,5].every( function(item) { return <=5 })       // true

[2,4,5,2,5].every( function(item) { return < 5 })       // false
```

```
var scores = []

var newScores = scores.map( function(score) { return score +1 })
var havePassedAll = scores.map( function(score) { return score >= 5 })
var isThereSome10 = scores.map( function(score) { return score === 10 })
var failedScores = scores.map( function(score) { return score <5 })

var averageScores = newScores.reduce (function(acc, item) {
    return acc + item
},0) / newScores.length
```

**ECMAScript-2015:**

```
// -------------------------------------

function addOne(score) { return score + 1 }
var addOne = score => score++

// -------------------------------------

var newScores = scores.map( score => score + 1 )
var havePassedAll = newScores.every( score => score >= 5 )
var isThereSome10 = newScores.some( score => score === 10 )
var failedScores = newScores.filter( score => score < 5  )
```

## reduce()

we pass two parameters: the function and an initial argument

```
[2,4,2,5,2,5,2,5,2,5,2].reduce(function(acc, item) {
    return acc + item
}, 0)
```

==> INSERT 13/04 STACK NOTES

## PROTOTYPE

`Prototype` is  a _property_ of a _function_

```
function person(gender){
    this.gender = gender
}
var person1 = new person('Male')
var person2 = new person('Femal')

person.prototype.type = 'Human Being'
person1.type
person2.type
```

# PROTOTYPE BURNT MY BRAINS