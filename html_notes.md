# HTML

`HTML` is a markup language and means _hyper text markup language_.

`a (href = x)` link documents and is the most important tag.

`www` means world wide web. The spider web of linked elements.

`HTML` gives semanthic info, the _format_ and _structure_ of the text; and has `tags` and `attributes`.

## Doctype

Indicates the html version and it's written in the first line.

`<!DOCTYPE html>` for __HTML5__

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">          // UTF-8 for occidental Codification 
    <title>Document</title>         // title showed on the tab
</head>
<body>                              // Content
    <h1>My main title</h1>
    <h2>My secondary title</2>
        <p>My paragraph with <strong>very important info</strong> </p>

    ul>li>a*4                       // + tab for develope

    <div></div> & <span></span>     // These don't have semanthic information

    <form></form><tab></tab>
</body>
</html>
```

## Layout

photo on JuanMa's notes

`<section>` content with meaningful information. Section can be found on <aside> too,

`<article>` has significance out from the blog.

`<aside>` information that doesn't need to have relation with the rest of the blog

## form

`<form>` the forms send data to a _server_ 
    - `action` = 'https://mydomain.com/contact.php'. Action is where the information goes.
    - `method` = method we are going to use.
        + `POST`
        + `GET`

Inside of **form**
    - `input`
    - `select`
    - `textarea`
    - `button` 

**i.e.**

```
<form action="/contact" method="POST">
    <fieldset>
        <legend>Create a New User</legend>
        <div>
            <label>Username</label>
            <input type="text" name="username" placeholder="Enter your user name">
        </div>
        <button>Send</button>                           // Button
        <input type="submit" value="Send Data!">        // Same Button
    </fieldset>
</form>
```

## Bibliography

- [The global structure of an HTML document](https://www.w3.org/TR/html401/struct/global.html)

- [Review of Basic HTML Tags](https://www.lehigh.edu/~inwww/old_seminar/tagreview.html)

- [Beautiful page](http://www.csszengarden.com/)

- [Complete Guide](http://learn.shayhowe.com/html-css/getting-to-know-html/) 

- [HTML Semantics](https://www.diigo.com/annotated/0ec7a7e13ad9c32a222e40dfad1fab47)

- [Lay-Out](http://www.developer.com/lang/understanding-the-proper-way-to-lay-out-a-page-with-html5.html)

- [Structural Semantics](https://www.smashingmagazine.com/2013/01/the-importance-of-sections/)

- [Typography Based Blog Layout in HTML5](https://line25.com/tutorials/create-a-typography-based-blog-layout-in-html5)

- [Lists](http://learn.shayhowe.com/html-css/creating-lists/)

- [Tables](http://learn.shayhowe.com/html-css/organizing-data-with-tables/)

- [Design HTML](https://www.smashingmagazine.com/2009/08/designing-a-html-5-layout-from-scratch/)