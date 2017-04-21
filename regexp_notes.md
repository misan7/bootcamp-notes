# RegExp Patterns of Chars

A regular expression is an `object` that describes a **pattern of characters**.

Regular expressions are used to perform pattern-matching and _search-and-replace_ functions on text.

**i.e.**
```javascript
var myRegExp = new RegExp("j.*t")

myRegExp.test("javascript") // true
myRegExp.test("jst")        // true
myRegExp.test("JavaScript") // false
```

It returns `true` if the text is between `j` and `t`. An _expression_ always return `true/false` and is **key sensitive**.

```javascript
/j.t*/.test("javascript")   // true
```

## It has 3 modificators

- `g` = __global__; with false, by default, it returns only the first element that is found. With true return all the found elements

- `m` = __multiline__; with true it does the search in several lines (false by default)

- `i` = __ignore case__; with true it does the matching sensitive to uppercase (false by default)

```javascript
var re = new RegExp('j.t*', 'gmt')
re.test("JavasripT is the best")    // true
```

**Types:**

```javascript
var re = new RegExp('j.t*', 'gmt')
var re2 = /j.t*/ig
```

- `.test()` = returns _true_ or _false_ if the expression follows a pattern.

```javascript
function isVowel(myChar) {
    return /aeiou/.test(myChar)
}
isVowel("a")        // true
isVowel("c")        // false
```
```
"HelloJavaScriptWorld".match(/j.t*/g)   // null
"HelloJavaScriptWorld".match(/j.t*/gi)   // [JavaScript]
```

- `match()`: Return an array of occurrences

- `search()`: Return the position of the first occurrence

- `replace()`: Allow us to replace the found string by another string

- `split()`: Accepts a regular expression to split a string in elements of an array

## More info about RegExp

- [JuanMa Notes](https://github.com/juanmaguitar/javascript-notes/tree/master/markdown-en/08-regular-expressions)

## Hungarian Notation examples

Hungarian Notation: the name of a variable or function indicates its _intention_ or _kind_.

- `nAge` = 8;

- `sName` = "Sergio"

- `bIsBlack` = true;

- `oFreq` = [object]