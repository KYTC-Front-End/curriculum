
# Welcome To The Responsive Design Workshop!
This workshop is designed for **helping you out with understanding responsive design** and how to apply it in action using **relative units**, **media queries** and **responsive images** in CSS, throughout the workshop, you will learn about these things and in the end, there will be some helpful **exercise** so you can practice them in a good way.


## What is Responsive Design
*Responsive design* is a way to approach designing your applications that is mindful of the fact that users don't all have screens of the same size. With a responsive design, the goal is to make your site beautiful for users on a variety of devices, while minimizing the amount of CSS you need to write.


## How to apply Responsive Design?

To start making responsive designs that look good on all screen sizes you should know the following:

### 1. Devices Sizes/Break Points

You need to be aware of the devices your users are using so you can target those devices screen sizes within your code as something we call ***breakpoints*** which we will take a look at later in the Media Queries part.

A good way to do this is to group all devices of the same kind under one break point that covers them all, for example:

- **Phones**: under 600px
- **Tablets(Portrait Mode)**: under 900px
- **Tablets (LandScape Mode)**: under 1200px
- **Desktops/Laptops**: under 1800px
- **Big Desktops/Screens**: above 1800px

Here is a simple graph of how this looks like
![devices sizes](https://i.imgur.com/36eTzkU.jpg)


### 2. Media Queries

Media queries are CSS instructions that are important for creating responsive web pages. Media queries allow content to adapt to various screen resolutions, with different CSS instructions being used for different screen sizes

```css
@media screen and (max-width: 600px) {
    /* Your styles go here */
}
```

**Using media queries**: 
Using the syntax of the media query above, as you can see you need to specify a breakpoint using `max-width` or `min-width` so your styles can apply for the given width

What's the difference between`max-width` and `min-width`?
- The `min-width` property sets a minimum browser or screen width that a certain set of styles would apply to.
-  The `max-width property` does just the opposite. it sets a maximum browser or screen width that a certain set of styles would apply to

 The `min-width` and `max-width` properties can be used together to create a media query that applies to screens within a rage
 
 ```css
 @media (min-width: 600px) and (max-width: 900px) {
  /* Your styles go here */
 }
 ```
 The above media query would apply to screens that have a minimum width of 600px and max-width of 900px 
 
**Media query example**:

```css
p {
    font-size: 24px;
}

@media (max-width: 1200px) {
    font-size: 16px;
}

@media (max-width: 600px) {
    font-size: 14px;
}
```
**Try to figure out** what happens to the `p` element font size in the Desktop, tablet and mobile screen? 

> Basically what happens is that the font size decreases each time our screen size decreases 


Here is a graph that shows how we would apply media queries to various devices

![media queries sample](https://i.imgur.com/XZNcs1t.jpg)

### 3. Relative Units 
*Relative units*, as the name suggests, are always relative to the length/size of another property. A relative unit gets sizing from something else.

> Most browsers specify a root font-size for the pages (16px)

`Percentages %`: it sets the width/font-size of the element relative to its parent's width/font-size

`rem`: it's relative to the root (i.e. HTML) element. This means that 1rem corresponds to the same size everywhere on the page (with font sizes and lengths).

`em`: this one is a bit tricky, it's relative to the font-size of the element itself when setting lengths but it's relative to the parent element when setting the font-size

`vh`: it's relative to the viewport's height (ie. 1vh = 1/100 of the viewport's height)

`vw`: it's relative to the viewport's width (ie. 1vw = 1/100 of the viewport's width)

**Quick Example**:

```css

div {
    font-size: 10px;
}

div p {
    font-size: 2em; /* 20px */
    padding: 1em; /* 20px */
}

div p span {
    font-size: 1rem; /* 16px */
    padding: 2rem; /* 16 * 2 = 36px */
}

```

> In the example above we have div element what has a p element inside it and a span element, as you may have noticed that the em unit when setting the font-size it was relative to the parent element but when setting the padding(a length) it was relative to the font-size of the element itself, and the rem was always relative to the root element font-size


### 4. Responsive images
There are two approaches to use images in your web page:
- Using the `<img />` tag 
- Setting it as a background for a `div`

When using images you want to make sure that they scale up and down or at least scale down so they don't look bad on smaller screens 

To scale it both up and down, we set the width to 100%:
```css
.responsive-img {
  width: 100%;
}
```

To scale it only down, we set the max-width to 100%

```css
.responsive-img {
  max-width: 100%;
}
```

There is more about responsive images, I just mentioned the basics of it in this workshop, for more checkout [this blog post](https://css-tricks.com/responsive-images-css/) on responsive images 

### 5. Responsive Design Strategies

**Desktop First**
- Start writing CSS for the desktop: large screen
- Then, media queries shrink design to smaller screens.

**Mobile First**
- Start writing CSS for mobile devices: small screen
- Then, media queries expanded design to larger screens

**Which one should you use?**

It depends on your project and the users devices, for example, mobile-first apps are optimized for the mobile experience and it results in faster web apps and desktop-first is Relatively quick, and it gives you more room for creative layouts.
> So you'ed better decide what's best for the project and you and if you have team members you should decide together 

![Desktop VS Mobile](https://i.imgur.com/3gkoQvX.jpg)

### 6. Testing your media queries

We test out our web pages using the dev tools in Chrome or in any browser you prefer, for this small exercise go on any responsive web page to carry on

1. Press `ctrl`+ `shift`+ `i` to open up the dev tools
2. Press on the responsive icon next to the cursor icon
3. Select which device you would like to see your page on
4. Select `Responsive` and resize the window to check for different screens at the same time
5. The colored lines show your media queries when you click on any of them you shall see the media query effect
> These may not appear at first so you need to press on the menu next to the cursor and then on show media queries 

![dev-tools](https://i.imgur.com/VciFQQ1.gif)

In the frame is **w3school's** Band template, you can check the demo [here](https://www.w3schools.com/w3css/tryw3css_templates_band.htm)

## Excercise 
1. Download the Repo   
2. `cd` into the folder  
3. Go to the media.css file 
4. Make the page responsive

**Hints**:
- You can look at how the result should look like [by clicking this link](https://mediaqueri.es/rwd/) 
- You probably should go to the styles.css file so you can see how the desktop version is made and that will make it way **much easier on you** to make it responsive!
   
   
    

## Usefull Resources :books: 
[The CSS Workshop - Relative Units](https://thecssworkshop.com/lessons/relative-units)

[GeeksForGeeks - What is the difference between screen and only](https://www.geeksforgeeks.org/what-is-the-difference-between-screen-and-only-screen-in-media-queries/)

[The Content Works - Media Queries](https://thecontentworks.uk/media-queries/)

[FROONT - 9 basic principles of responsive web design](https://blog.froont.com/9-basic-principles-of-responsive-web-design/)

[Smashing Magazine - Responsive Web Design - What It Is And How To Use It](https://www.smashingmagazine.com/2011/01/guidelines-for-responsive-web-design/)

[Rithmschool - Responsive Design](https://www.rithmschool.com/courses/intermediate-css-bootstrap/responsive-design)
