## HTML Basic 
### HTML page structure 
![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20220401160946/HTML-Basic-Format-768x534.png)

```<!DOCTYPE html>``` : This is the document type declaration (not technically a tag). It declares a document as being an HTML document. The doctype declaration is not case-sensitive.

```<html>```: This is called the HTML root element. All other elements are contained within it.

```<head>```:  The head tag contains the “behind the scenes” elements for a webpage. Elements within the head aren’t visible on the front-end of a webpage. HTML elements used inside the <head> element include:

-   ```<style>``` :This html tag allows us to insert styling into our webpages and make them appealing to look at with the help of CSS.
-   ```<title>``` :The title is what is displayed on the top of your browser when you visit a website and contains title of the webpage that you are viewing.
-  ```<script>```:This tag is used to add functionality in the website with the help of JavaScript.
-   ```<link>```: The ‘link’ tag is used to tie together HTML, CSS and JavaScript. It is self closing.

```<body>```:  The body tag is used to enclose all the visible content of a webpage. In other words, the body content is what the browser will show on the front-end.

An HTML document can be created using any text editor. Save the text file using  **.html**  or  **.htm**. Once saved as an HTML document, the file can be opened as a webpage in the browser.

### Anatomy of an HTML element
![enter image description here](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)


The main parts of our element are as follows:

1.  **The opening tag:**  This consists of the name of the element (in this case, p), wrapped in opening and closing  **angle brackets**. This states where the element begins or starts to take effect — in this case where the paragraph begins.
2.  **The closing tag:**  This is the same as the opening tag, except that it includes a  _forward slash_  before the element name. This states where the element ends — in this case where the paragraph ends. Failing to add a closing tag is one of the standard beginner errors and can lead to strange results.
3.  **The content:**  This is the content of the element, which in this case, is just text.
4.  **The element:**  The opening tag, the closing tag, and the content together comprise the element.


Elements can also have attributes that look like the following:

![enter image description here](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

Attributes contain extra information about the element that you don't want to appear in the actual content


### Inspect an HTML Element:

Right-click on an element (or a blank area), and choose "Inspect" or "Inspect Element" to see what elements are made up of (you will see both the HTML and the CSS). You can also edit the HTML or CSS on-the-fly in the Elements or Styles panel that opens.



