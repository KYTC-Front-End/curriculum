
## # CSS  Syntax

A style rule set consists of a selector and declaration block.

![enter image description here](https://i.ibb.co/wLNX3pD/Screenshot-2023-04-17-031742.png)
-   The selector points to the HTML element you want to style.
-   The declaration block contains one or more declarations separated by semicolons.
-   Each declaration includes a CSS property name and a value, separated by a colon.  
    For Example:
-    `h1`  is a selector in CSS (it points to the HTML element you want to style: `<h1>`).
-   `color`  is a property, and  `blue`  is the property value.

  CSS declaration always ends with a semicolon, and declaration blocks are surrounded by curly braces.
**Example :**  In the following example all p elements will be center-aligned, with a blue text color:

-   CSS

`p {``color``: blue``;``text-align``:``center``;}`

**the output** 
![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Screenshot-13-7-1-e1543575046158.png)

## CSS Selectors 
CSS selectors are used to “find” (or select) HTML elements based on their element name, id, class, attribute, and more.

**1.**  **UNIVERSAL SELECTORS:** Rather than selecting elements of a specific type, the universal selector quite simply matches the name of any element type
`* {``color``:``#000000``;``}`
**Output:**  This rule renders the content of every element in our document in black.

**2.ELEMENT SELECTORS:** The element selector selects elements based on the element name. You can select all p elements on a page like this (in this case, all p elements will be center-aligned, with a red text color).

`p {``text-align``:``center``;``color``:``red``;``}`

**Output:**

![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Screenshot-15-5-1.png)

**3.DESCENDANT SELECTORS:** Suppose you want to apply a style rule to a particular element only when it lies inside a particular element. As given in the following example, the style rule will apply to the li element only when it lies inside the ul tag.

    ul li{
	color: #000000;
	}

** 4. ID SELECTORS:**

-   The id selector uses the id attribute of an HTML element to select a specific element.
-   The id of an element should be unique within a page, so the id selector is used to select one unique element!
-   To select an element with a specific id, write a hash (#) character, followed by the id of the element.
-   The style rule below will be applied to the HTML element with id=”para1″:

  `  #para1{
    color: green;
    text-align: center;
    }`
    ![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20220718125509/Screenshot-2022-07-18-125458.png)

**5.CLASS SELECTORS:**

-   The class selector selects elements with a specific class attribute.
-   To select elements with a specific class, write a period (.) character, followed by the name of the class.
-   In the example below, all HTML elements with class=”center” will be green and center-aligned:

You can apply more than one class selector to a given element. Consider the following example:

    .gfg{color: green;text-align: center;}

**6.GROUPING SELECTORS**  If you have elements with the same style definitions, like this:

-   CSS
  ``` 
   h1 {
text-align: center;
color: blue;
}
h2 {
text-align: center;
color: blue;
}
p {
text-align: center;
color: blue;
} 
```
It will be better to group the selectors, to minimize the code. To group selectors, separate each selector with a comma. In the example below we have grouped the selectors from the code above:

   ```
    h1, h2, p {
text-align: center;
color: red;
}
```
![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Screenshot-19-5-1.png)











