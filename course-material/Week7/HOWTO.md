
## # How To Add CSS

When a browser reads a style sheet, it will format the HTML document according to the information in the style sheet.

## Three Ways to Insert CSS

There are three ways of inserting a style sheet:

-   External CSS
-   Internal CSS
-   Inline CSS

## Inline CSS

An inline style may be used to apply a unique style for a single element.

To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.
```
<!DOCTYPE html>  
<html>  
<body>  
  
<h1 style="color:blue;text-align:center;">This is a heading</h1>  
<p style="color:red;">This is a paragraph.</p>  
  
</body>  
</html>
```

**Tip:**  An inline style loses many of the advantages of a style sheet (by mixing content with presentation). Use this method sparingly.

## Internal CSS

An internal style sheet may be used if one single HTML page has a unique style.

The internal style is defined inside the <style> element, inside the head section.
Internal styles are defined within the <style> element, inside the <head> section of an HTML page:
```
<!DOCTYPE html>  
<html>  
<head>  
<style>  
body  {  
background-color:  linen;  
}  
  
h1  {  
color:  maroon;  
margin-left:  40px;  
}  
</style>  
</head>  
<body>  
  
<h1>This is a heading</h1>  
<p>This is a paragraph.</p>  
  
</body>  
</html>
```


## External CSS

With an external style sheet, you can change the look of an entire website by changing just one file!

Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.
External styles are defined within the <link> element, inside the <head> section of an HTML page:

```
<!DOCTYPE html>  
<html>  
<head>  
<link rel="stylesheet"  href="mystyle.css">  
</head>  
<body>  
  
<h1>This is a heading</h1>  
<p>This is a paragraph.</p>  
  
</body>  
</html>
```

An external style sheet can be written in any text editor, and must be saved with a .css extension.

The external .css file should not contain any HTML tags.

Here is how the "mystyle.css" file looks:
### "mystyle.css"
```
body {  
background-color:  lightblue;  
}  
  
h1 {  
color:  navy;  
margin-left:  20px;  
}
```
**Note:** Do not add a space between the property value (20) and the unit (px):  
Incorrect (space): `margin-left: 20 px;`  
Correct (no space): `margin-left: 20px;`


## Multiple Style Sheets
If some properties have been defined for the same selector (element) in different style sheets, the value from the last read style sheet will be used.
Assume that an  **external style sheet**  has the following style for the `<h1>` element:
```
h1 {  
color:  navy;  
}
```
Then, assume that an  **internal style sheet**  also has the following style for the `<h1>` element:
```
h1 {  
color:  orange;  
}
```
If the internal style is defined  **after**  the link to the external style sheet, the `<h1>` elements will be "orange":
```
<head>  
<link rel="stylesheet"  type="text/css"  href="mystyle.css">  
<style>  
h1  {  
color:  orange;  
}  
</style>  
</head>
```
However, if the internal style is defined  **before**  the link to the external style sheet, the `<h1>` elements will be "navy":
```
<head>  
<style>  
h1  {  
color:  orange;  
}  
</style>  
<link rel="stylesheet"  type="text/css"  href="mystyle.css">  
</head>
```
## Cascading Order

What style will be used when there is more than one style specified for an HTML element?

All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

1.  Inline style (inside an HTML element)
2.  External and internal style sheets (in the head section)
3.  Browser default

So, an inline style has the highest priority, and will override external and internal styles and browser defaults.



