


# HTML  class Attribute
The HTML  `class`  attribute is used to specify a class for an HTML element.

Multiple HTML elements can share the same class.
The  `class`  attribute is often used to point to a class name in a style sheet. It can also be used by a JavaScript to access and manipulate elements with the specific class name.

In the following example we have three  `<div>`  elements with a  `class`  attribute with the value of "city". All of the three  `<div>`  elements will be styled equally according to the  `.city`  style definition in the head section:

    <body>  
      
    <div class="city">  
    <h2>London</h2>  
    <p>London is the capital of England.</p>  
    </div>  
      
    <div class="city">  
    <h2>Paris</h2>  
    <p>Paris is the capital of France.</p>  
    </div>  
      
    <div class="city">  
    <h2>Tokyo</h2>  
    <p>Tokyo is the capital of Japan.</p>  
    </div>  
      
    </body>
    
   ## Multiple Classes
   HTML elements can belong to more than one class.

To define multiple classes, separate the class names with a space, e.g. <div class="city main">. The element will be styled according to all the classes specified.

In the following example, the first  `<h2>`  element belongs to both the  `city`  class and also to the  `main`  class, and will get the CSS styles from both of the classes:

    <h2 class="city main">London</h2>  
    <h2 class="city">Paris</h2>  
    <h2 class="city">Tokyo</h2>

**Tip:**  The  `class`  attribute can be used on  **any**  HTML element.

**Note:**  The class name is case sensitive!

# HTML  id Attribute
The HTML  `id`  attribute is used to specify a unique id for an HTML element.

You cannot have more than one element with the same id in an HTML document.
The  `id`  attribute specifies a unique id for an HTML element. The value of the  `id`  attribute must be unique within the HTML document.

The  `id`  attribute is used to point to a specific style declaration in a style sheet. It is also used by JavaScript to access and manipulate the element with the specific id.
In the following example we have an `<h1>` element that points to the id name "myHeader".

    <h1 id="myHeader">My Header</h1>
**Note:**  The id name is case sensitive!

## Difference Between Class and ID

A class name can be used by multiple HTML elements, while an id name must only be used by one HTML element within the page

## HTML Bookmarks with ID and Links

HTML bookmarks are used to allow readers to jump to specific parts of a webpage.

Bookmarks can be useful if your page is very long.

To use a bookmark, you must first create it, and then add a link to it.

Then, when the link is clicked, the page will scroll to the location with the bookmark.

## Example

First, create a bookmark with the `id` attribute:

    <h2 id="C4">Chapter 4</h2>
Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:

    <a href="#C4">Jump to Chapter 4</a>
Or, add a link to the bookmark ("Jump to Chapter 4"), from another page:

    <a href="html_demo.html#C4">Jump to Chapter 4</a>



