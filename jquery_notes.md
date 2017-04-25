# jQuery: The Browser Environment

`DOM` = document object model; how we see HTML from JavaScript.

How behaves JavaScript on the Server's environment?

The Javascript code in a webpage has access to a few objects. These ojects can be grouped in:

- Objects related to the loaded HTML page (the document). These objects form the **Document Object Model** (DOM)
- Objects that are related with things that happen out of the page (the windows' browser and the screen). These objects form the **Browser Object Model** (BOM)

The JS code that we use in a webpage allows us to acces to objects in the browser and... I'm sleepy.

When we load an HTML we have some **methods** and **propiertes** for interactuate with the **DOM**.

`BOM` = Browser Object Model; items included on the window, outside from the document.

![](https://raw.githubusercontent.com/juanmaguitar/javascript-notes/master/markdown-en/11-browser-environment/img/bom.png)]

All global things have to be specified like this:

```html
<script type="text/javascript">
    windows.mySuperNumber = 456;
    console.log(mySuperNumber);
</script>
```

## window properties

Some of the objects objects we have available in are:

- `window.navigator` = Object that contains information about the browser:

```
>>>>window.navigator.userAgent
"Mozilla/5.0 (Windows; U; Windows NT 5.1; es-ES; rv:1.9.2.12)
Gecko/20101026 Firefox/3.6.12 ( .NET CLR 3.5.30729)"
```

- ```window.location``` = is an objects that contains info (and methods) about the current URL

```
>>> window.location.href = 'http://www.packtpub.com'
>>> location.href = 'http://www.packtpub.com'
>>> location = 'http://www.packtpub.com'
>>> location.assign('http://www.packtpub.com')
>>> location.reload()
>>> window.location.href = window.location.href
>>> location = location
```

- `window.history` = is an object that contains the history of visited pages and it has methods to move around themm (without thee possibility of seeing the URL’s)

```
>>> window.history.length
5
>>> history.forward()
>>> history.back()
>>> history.go(-2);
```

- `window.frames` = is a colection of all the frames that are in the page. Every frame has its own window object. We can use parent to access the parent frame from the children frame. With the property top we can access the page in top of all the frames. We can access a concrete frame by its name.

```
<iframe name="myframe" src="about:blank" />
>>> window.frames[0]
>>> frames[0].window.location.reload()
>>> frames[0].parent === window
true
>>> window.frames[0].window.top === window
true
>>> self === window
true
>>> window.frames['myframe'] === window.frames[0]
true
```

- `window.screen` = offers info about the screen (general, out of the browser)

```
>>> window.screen.colorDepth
32
>>> screen.width
1440
>>> screen.availWidth
1440
>>> screen.height
900
>>> screen.availHeight
847
```

## window methods

Some of the method available in window are:

- `window.open(), window.close()` allow us to open and close new windows (popups)
`window.open()` returns a reference to the opened window (it it returns false that means the window couldn't be created - popups blocked)
Its use is not recommended ;-)

```
>>> var win = window.open('http://www.packtpub.com', 'packt',
'width=300,height=300,resizable=yes');
>>> win.close()
```

- `window.moveTo(), window.moveBy(), window.resizeTo(), window.resizeBy()` alow us to move and re-dimension the windows
Its use is not recommended ;-)

```
>>> window.moveTo(100, 100)
>>> window.moveBy(10, -10)
>>> window.resizeTo(300, 300)
>>> window.resizeBy(20, 10)
```

- `window.alert(), window.prompt(), window.confirm()` allow us to interact with the user through system messages

```javascript
if (confirm('Are you sure you want to delete this item?')) {
// delete
} else {
// abort
}
>>> var answer = prompt('And your name was?');
console.log(answer);
```

- `window.setTimeout(), window.setInterval()` allow us to execute codigo after a time interval (and repeat it if we want)

```
>>> function boo(){alert('Boo!');}
>>> setTimeout(boo, 2000);
>>> var id = setTimeout(boo, 2000);
>>> clearTimeout(id);
>>> function boo() { console.log('boo') };
>>> var id = setInterval( boo, 2000 );
boo
boo
boo
>>> clearInterval(id)
var id = setInterval( "alert('boo, boo')", 2000 );
var id = setInterval( function(){ alert('boo, boo')}, 2000 );
```

- `window.document` = is a BOM object with info about the current document **All** the methods and properties inside window.document belong to the DOM objects category

## The DOM (Document Object Model) 

The DOM is a way of representing a HTML document (or XML) like a **tree of nodes.**
By using DOM methods and properties we can access the page elements, modify them, remove them or adding new ones.

## jQuery

**jQuery might be load before our JavaScript code.** 

[Download](http://jquery.com/download/) from the webpage or search the **cdn** (`https://code.jquery.com/jquery-3.2.1.js`)

```
$() = jQuery()
```

## Selecting Elements

![selectors](images/selectors.png)

- [More info](http://learn.jquery.com/using-jquery-core/selecting-elements/)

#### Refining & Filtering Selections

Sometimes the selection contains more than what you're after. jQuery offers several methods for refining and filtering selections.

![Refining](images/refining_jquery.png)

## Getting and Setting Information About Elements

There are many ways to change an existing element. Among the most common tasks is changing the inner HTML or attribute of an element. jQuery offers simple, cross-browser methods for these sorts of manipulations. You can also get information about elements using many of the same methods in their getter incarnations. For more information on getters and setters, see the Working with Selections section. Here are a few methods you can use to get and set information about elements:

- `.html()` – Get or set the HTML contents.
- `.text()` – Get or set the text contents; HTML will be stripped.
- `.attr()` – Get or set the value of the provided attribute.
- `.width()` – Get or set the width in pixels of the first element in the selection as an integer.
- `.height()` – Get or set the height in pixels of the first element in the selection as an integer.
- `.position()` – Get an object with position information for the first element in the selection, relative to its first positioned ancestor. This is a getter only.
- `.val()` – Get or set the value of form elements.

---

- [Link to append and appendTo](http://learn.jquery.com/using-jquery-core/manipulating-elements/#creating-new-elements)

---

- `append` = we select the father and after the element we want to append

- `appenTo-` = we selet the element and after the father where we will append the element.

```javascript
$('#myList').append( $('.ringo'))
$('.ringo').appendTo('#myList')
```

---

- [Link to Cloning and removing elements](http://learn.jquery.com/using-jquery-core/manipulating-elements/#cloning-elements)

--- 

#### jQuery Example of dynamic List

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <!-- Latest compiled and minified CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
  <style type="text/css">


  </style>
</head>
<body>

  <div class="container">
    <ul class="list-group" id="myList"></ul>
  </div>


  <script type="text/javascript" src="https://code.jquery.com/jquery-3.2.1.js"></script>

  <script type="text/javascript">
    var beatles = ['john','paul','george','ringo']
    var htmlList = ''
    beatles.forEach( function(name, i) {
      htmlList += '<li class="list-group-item">' + name + '</li>'
      console.log(htmlList)
    })
    console.log( typeof htmlList )
    $('#myList').html(htmlList)
  </script>
</body>
</html>
```

#### Several ways of List Elements

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <!-- Latest compiled and minified CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
  <style type="text/css">
    .highlight { background: black; color: white; }
  </style>

</head>
<body>
  <div class="container">
    <ul class="list-group" id="myList"></ul>
  </div>


  <script type="text/javascript" src="https://code.jquery.com/jquery-3.2.1.js"></script>

  <script type="text/javascript">
    // *** Way 1 ***
    // var liItems = []
    // for (var i=1; i<=20; i++) {
    //   liItems.push('<li class="list-group-item">' + i + '</li>')
    // }
    // $("#myList").html( liItems.join('') )

    // *** Way 2 ***
    // for (var i=1; i<=20; i++) {
    //   $('#myList').append( $('<li class="list-group-item">item ' + i + '</li>') )
    // }

    // *** Way 3 ***
    // for (var i=1; i<=20; i++) {
    //   var $item = $('<li class="list-group-item">row ' + i + '</li>')
    //   $item.appendTo('#myList')
    // }

    // *** Way 4 ***
    // var listHtml = ''
    // for (var i=1; i<=20; i++) {
    //   listHtml += '<li class="list-group-item">elem ' + i + '</li>'
    // }
    // $("#myList").html(listHtml )

    // *** Way 5 ***
    var listHtml = new Array(20).fill(0).map(function(_,i) { return '<li class="list-group-item">elem ' + (i+1) + '</li>'})
    $("#myList").html(listHtml )
    var $listElemes = $("#myList li");

    $listElemes.filter(':even').addClass('highlight')


  </script>
</body>
</html>
```

## Traversing

#### Parents

The methods for finding the parents from a selection include `.parent()`, `.parents()`, `.parentsUntil()`, and `.closest()`

```html
<div class="grandparent">
    <div class="parent">
        <div class="child">
            <span class="subchild"></span>
        </div>
    </div>
    <div class="surrogateParent1"></div>
    <div class="surrogateParent2"></div>
</div>
```

```javascript
// Selecting an element's direct parent:
 
// returns [ div.child ]
$( "span.subchild" ).parent();
 
// Selecting all the parents of an element that match a given selector:
 
// returns [ div.parent ]
$( "span.subchild" ).parents( "div.parent" );
 
// returns [ div.child, div.parent, div.grandparent ]
$( "span.subchild" ).parents();
 
// Selecting all the parents of an element up to, but *not including* the selector:
 
// returns [ div.child, div.parent ]
$( "span.subchild" ).parentsUntil( "div.grandparent" );
 
// Selecting the closest parent, note that only one parent will be selected
// and that the initial element itself is included in the search:
 
// returns [ div.child ]
$( "span.subchild" ).closest( "div" );
 
// returns [ div.child ] as the selector is also included in the search:
$( "div.child" ).closest( "div" );
```

#### Children

The methods for finding child elements from a selection include `.children()` and `.find()`. The difference between these methods lies in how far into the child structure the selection is made. `.children()` only operates on direct child nodes, while `.find()` can traverse recursively into children, children of those children, and so on.

```javascript
// Selecting an element's direct children:
 
// returns [ div.parent, div.surrogateParent1, div.surrogateParent2 ]
$( "div.grandparent" ).children( "div" );
 
// Finding all elements within a selection that match the selector:
 
// returns [ div.child, div.parent, div.surrogateParent1, div.surrogateParent2 ]
$( "div.grandparent" ).find( "div" );
```

#### Siblings

The rest of the traversal methods within jQuery all deal with finding sibling selections. There are a few basic methods as far as the direction of traversal is concerned. You can find previous elements with `.prev()`, next elements with `.next()`, and both with `.siblings()`. There are also a few other methods that build onto these basic methods: `.nextAll()`, `.nextUntil()`, `.prevAll()` and `.prevUntil()`.

```javascript
// Selecting a next sibling of the selectors:
 
// returns [ div.surrogateParent1 ]
$( "div.parent" ).next();
 
// Selecting a prev sibling of the selectors:
 
// returns [] as No sibling exists before div.parent
$( "div.parent" ).prev();
 
// Selecting all the next siblings of the selector:
 
// returns [ div.surrogateParent1, div.surrogateParent2 ]
$( "div.parent" ).nextAll();
 
// returns [ div.surrogateParent1 ]
$( "div.parent" ).nextAll().first();
 
// returns [ div.surrogateParent2 ]
$( "div.parent" ).nextAll().last();
 
// Selecting all the previous siblings of the selector:
 
// returns [ div.surrogateParent1, div.parent ]
$( "div.surrogateParent2" ).prevAll();
 
// returns [ div.surrogateParent1 ]
$( "div.surrogateParent2" ).prevAll().first();
 
// returns [ div.parent ]
$( "div.surrogateParent2" ).prevAll().last();
```

- [More information about traversing](http://learn.jquery.com/using-jquery-core/traversing/)

## Iterating over jQuery and non-jQuery Objects

[More info](http://learn.jquery.com/using-jquery-core/iterating/)


## Events

Every action (click, change...) that happens in the browser is comunicated in the form of an event. We can hear these events and associate a function that will be executed when the event occurs with JavaScript.

**i.e.** a console.log appears in the dev tools when you click a button.

```html
<script type="text/javascript">
    $('button').on(click, function() {
        console.log("The button was clicked")
    })
</script>
```

`Bubbling` = when you click on events, they take effect on all the superior layers.

!! Really Important
```javascript
$('body').on('click', function(e) {
    console.log(e)          // The event
    console.log(this)       // Event resolution, it refers to body in this case
    console.log(e.target)   // The element that provokes the event
})
```

```javascript
$('ul').on('click', 'li',function () {
    e.preventDefault();
    alert( $(this).text() )
})
```

