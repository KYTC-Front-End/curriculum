## String Methods 
In JavaScript, the textual data is stored as strings. There is no separate type for a single character.

Let’s recall the kinds of quotes.

Strings can be enclosed within either single quotes, double quotes or backticks:

```javascript 
let single =  'single-quoted';
let double =  "double-quoted";
let backticks = `backticks`;
```
Single and double quotes are essentially the same. Backticks, however, allow us to embed any expression into the string, by wrapping it in  `${…}`:

Another advantage of using backticks is that they allow a string to span multiple lines:

```javascript 
let guestList =  `
Guests: * John
 * Pete
  * Mary 
  * `;
```
## Special characters

It is still possible to create multiline strings with single and double quotes by using a so-called “newline character”, written as  `\n`, which denotes a line break:

```javascript 
let guestList =  "Guests:\n * John\n * Pete\n * Mary";  
alert(guestList);  // a multiline list of guests, same as above
```

As a simpler example, these two lines are equal, just written differently:
```javascript 
let str1 =  "Hello\nWorld";  // two lines using a "newline symbol"  // two lines using a normal newline and backticks 
 let str2 =  `Hello
  World
  `;  
 alert(str1 == str2);  // true
```
![enter image description here](https://i.ibb.co/rHgWSnK/Screenshot-2023-06-06-144628.png)

## String length
The  `length`  property has the string length:

```javascript
alert( `My\n`.length ); // 3
```
Note that  `\n`  is a single “special” character, so the length is indeed  `3`.
`length`  is a property

**Note**
People with a background in some other languages sometimes mistype by calling  `str.length()`  instead of just  `str.length`. That doesn’t work.

Please note that  `str.length`  is a numeric property, not a function. There is no need to add parenthesis after it. Not  `.length()`, but  `.length`.

## Accessing characters

To get a character at position  `pos`, use square brackets  `[pos]`  or call the method  [str.at(pos)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at). The first character starts from the zero position:

```javascript 
let str =  `Hello`;  
// the first character  
alert( str[0]  );  // H  
alert( str.at(0)  );  // H  
// the last character 
 alert( str[str.length -  1]  );  // o 
  alert( str.at(-1)  ); //o
```

As you can see, the  `.at(pos)`  method has a benefit of allowing negative position. If  `pos`  is negative, then it’s counted from the end of the string.

So  `.at(-1)`  means the last character, and  `.at(-2)`  is the one before it, etc.

The square brackets always return  `undefined`  for negative indexes, for instance:
```javascript 
let str =  `Hello`;  alert( str[-2]  );  // undefined 
 alert( str.at(-2)  );  // l
```
## Strings are immutable

Strings can’t be changed in JavaScript. It is impossible to change a character.

Let’s try it to show that it doesn’t work:
```javascript 
let str =  'Hi'; 
str[0]  =  'h';  // error 
 alert( str[0]  );  // doesn't work
```
The usual workaround is to create a whole new string and assign it to  `str`  instead of the old one.

For instance:
```javascript 
let str =  'Hi';
 str =  'h'  + str[1];  // replace the string 
  alert( str );  // hi
```

## Changing the case

Methods  [toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)  and  [toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)  change the case:

```javascript 
alert(  'Interface'.toUpperCase()  );  // INTERFACE 
 alert(  'Interface'.toLowerCase()  );  // interface
```
Or, if we want a single character lowercased:

```javascript
alert( 'Interface'[0].toLowerCase() ); // 'i'
```
## Searching for a substring

There are multiple ways to look for a substring within a string.

### [str.indexOf](https://javascript.info/string#str-indexof)

The first method is  [str.indexOf(substr, pos)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf).

It looks for the  `substr`  in  `str`, starting from the given position  `pos`, and returns the position where the match was found or  `-1`  if nothing can be found.

For instance:

```javascript 
let str =  'Widget with id';
  alert( str.indexOf('Widget')  );  // 0, because 'Widget' is found at the beginning  
  alert( str.indexOf('widget')  );  // -1, not found, the search is case-sensitive 
   alert( str.indexOf("id")  );  // 1, "id" is found at the position 1 (..idget with id)
```
The optional second parameter allows us to start searching from a given position.

For instance, the first occurrence of  `"id"`  is at position  `1`. To look for the next occurrence, let’s start the search from position  `2`:
```javascript 
let str =  'Widget with id'; 
 alert( str.indexOf('id',  2)  )  // 12
```
**Note **
There is also a similar method  [str.lastIndexOf(substr, position)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf)  that searches from the end of a string to its beginning.

It would list the occurrences in the reverse order.


There is a slight inconvenience with  `indexOf`  in the  `if`  test. We can’t put it in the  `if`  like this:
```javascript 
let str =  "Widget with id"; 
 if  (str.indexOf("Widget"))  { 
  alert("We found it");  // doesn't work!  
  }
```
The  `alert`  in the example above doesn’t show because  `str.indexOf("Widget")`  returns  `0`  (meaning that it found the match at the starting position). Right, but  `if`  considers  `0`  to be  `false`.

So, we should actually check for  `-1`, like this:
```javascript 
let str =  "Widget with id";
  if (str.indexOf("Widget") != -1)
   {
    alert("We found it");  // works now!  
    }
```
### includes, startsWith, endsWith
The more modern method  [str.includes(substr, pos)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)  returns  `true/false`  depending on whether  `str`  contains  `substr`  within.

It’s the right choice if we need to test for the match, but don’t need its position:

```javascript 
alert(  "Widget with id".includes("Widget")  );  // true  
alert(  "Hello".includes("Bye")  );  // false
```

The optional second argument of  `str.includes`  is the position to start searching from:
```javascript 
alert(  "Widget".includes("id")  );  // true 
 alert(  "Widget".includes("id",  3)  );  // false, from position 3 there is no "id
```

The methods  [str.startsWith](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith)  and  [str.endsWith](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)  do exactly what they say:

```javascript 
alert(  "Widget".startsWith("Wid")  );  // true, "Widget" starts with "Wid" 
 alert(  "Widget".endsWith("get")  );  // true, "Widget" ends with "get"
```
## Getting a substring

There are 3 methods in JavaScript to get a substring:  `substring`,  `substr`  and  `slice`.

`str.slice(start [, end])`

Returns the part of the string from  `start`  to (but not including)  `end`.

For instance:
```javascript 
let str =  "stringify"; 
 alert( str.slice(0,  5)  );  // 'strin', the substring from 0 to 5 (not including 5) 
  alert( str.slice(0,  1)  );  // 's', from 0 to 1, but not including 1, so only character at 0
```

If there is no second argument, then  `slice`  goes till the end of the string:
```javascript 
let str =  "stringify"; 
 alert( str.slice(2)  );  // 'ringify', from the 2nd position till the end
```

Negative values for  `start/end`  are also possible. They mean the position is counted from the string end:
```javascript 
let str =  "stringify";  // start at the 4th position from the right, end at the 1st from the right 
 alert( str.slice(-4,  -1)  );  // 'gif'
```
`str.substring(start [, end])`

Returns the part of the string  _between_  `start`  and  `end`  (not including  `end`).

This is almost the same as  `slice`, but it allows  `start`  to be greater than  `end`  (in this case it simply swaps  `start`  and  `end`  values).

For instance:

```javascript 
let str =  "stringify";  // these are same for substring  
alert( str.substring(2,  6)  );  // "ring" 
 alert( str.substring(6,  2)  );  // "ring" 
  // ...but not for slice: 
   alert( str.slice(2,  6)  );  // "ring" (the same) 
    alert( str.slice(6,  2)  );  // "" (an empty string)
```


Negative arguments are (unlike slice) not supported, they are treated as  `0`.

`str.substr(start [, length])`

Returns the part of the string from  `start`, with the given  `length`.

In contrast with the previous methods, this one allows us to specify the  `length`  instead of the ending position:
```javascript 
let str =  "stringify";
  alert( str.substr(2,  4)  );  // 'ring', from the 2nd position get 4 characters
```

The first argument may be negative, to count from the end:
```javascript 
let str =  "strin_gi_fy"; 
 alert( str.substr(-4,  2)  );  // 'gi', from the 4th position get 2 characters
```
Let’s recap these methods to avoid any confusion:

![enter image description here](https://i.ibb.co/Wkgnn7t/Screenshot-2023-06-06-string.png)



Strings also have methods for doing search/replace with regular expressions. But that’s big topic, so it’s explained in a separate tutorial section [Regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions).


There are several other helpful methods in strings:

-   `str.trim()`  – removes (“trims”) spaces from the beginning and end of the string.
-   `str.repeat(n)`  – repeats the string  `n`  times.
-   …and more to be found in the  [manual](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).
-   Concatenation: You can combine two or more strings together using the concatenation operator (+) or the `concat()` method. For example:
```javascript 
string1 = "Hello"
string2 = "World"
result = string1 + " " + string2
print(result)  # Output: Hello World

# Using concat() method
result = string1.concat(" ", string2)
print(result)  # Output: Hello World

```

