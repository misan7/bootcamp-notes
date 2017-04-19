# Regular Expressions

Regular expressions create a pattern to locate texts that follows a pattern or not. 

**i.e.**
```
var myRegExp = new RegExp("j.*t")

myRegExp.test("javascript") // true
myRegExp.test("jst")        // true
myRegExp.test("JavaScript") // false
```

It returns `true` if the text is between `j` and `t`. It returns `true/false` and is key sensitive.

```
/j.t*/.test("javascript")   // true
```

It has 3 _modificators_:

`g` = _global_; with false, by default, it returns only the first element that is found. With true return all the found elements

`m` = _multiline_; with true it does the search in several lines (false by default)

`i` = _ignore case_; with true it does the matching sensitive to uppercase (false by default)

var re = new RegExp('j.t*', 'gmt')
re.test("JavasripT is the best")    // true

Types:

var re = new RegExp('j.t*', 'gmt')

var re2 = /j.t*/ig

`.test` = returns true or false if the expression follows a pattern

function isVowel(myChar) {
    return /aeiou/.test(myChar)
}
isVowel("a")        // true
isVowel("c")        // false

```
"HelloJavaScriptWorld".match(/j.t*/g)   // null
"HelloJavaScriptWorld".match(/j.t*/gi)   // [JavaScript]
```

match()
search()            // important!! Example of Pulp Fiction Lore ipsum
replace()
split()

## Regular Expression Syntax

{n}

/[0-9]{2}-[0-9]{2}-[0-9]{4}/.test("02-03-2017")     // true

```
function charFreq(text) {
    for (var i = 0; i < text.length; i++){
        console.log(text[i])
    }
}

charFreq("juanma")

{
    "j": 1,
    "u": 1,
    "a": 2,
    "n": 1,
    "m": 1,
}
```

## hungar notation

nAge = 8;

sName = "Sergio"

bIsBlack = true;

oFreq = [object]



way 7

```
oFreq[char] = oFreq[char] ? oFreq[char]++ :1
```

If oFreq[char] exists return ++oFreq[char], if not return 1.

Links:

https://github.com/juanmaguitar/javascript-notes/tree/master/markdown-en/08-regular-expressions
