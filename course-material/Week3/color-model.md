## Color model

 1. HSL

HSL stands for Hue, Saturation, and Lightness, and is a color model used in computer graphics, image processing, and other related fields. HSL is similar to other color models such as HSV (Hue, Saturation, Value) and HSB (Hue, Saturation, Brightness), but it has some differences in how it defines color.

In the HSL color model, Hue represents the dominant color or wavelength and is usually measured in degrees on a color wheel from 0 to 360. Saturation refers to the purity or intensity of the color and is usually measured as a percentage from 0% (gray or no color) to 100% (fully saturated color). Lightness represents the perceived brightness of the color and is also usually measured as a percentage from 0% (black) to 100% (white).
Examples : 
**The HSL values for the color red are:**

   -   Hue: 0 or 360 (red is at the beginning and end of the hue spectrum)
  -   Saturation: 100% (fully saturated)
  -   Lightness: 50% (mid-range lightness, not too bright or too dark)

So the HSL representation of the color red would be hsl(0, 100%, 50%).
 **HSL values for the color baby blue are:**
-   Hue: around 195 degrees (which is a blue-green color)
-   Saturation: 53% (somewhat desaturated, but still with a moderate amount of colorfulness)
-   Lightness: 79% (fairly light, but not completely white)


 HSL is often used in computer programming and web development to specify colors in CSS (Cascading Style Sheets) and other languages. By adjusting the values of Hue, Saturation, and Lightness, designers can create a wide range of colors and color schemes for use in various applications.

![enter image description here](https://global.discourse-cdn.com/freecodecamp/original/3X/b/c/bc85e54f3ac40cb00e0adf468eefd09eebc34c70.png)
 
2. HSV '

HSV stands for Hue, Saturation, and Value, and is another color model used in computer graphics and related fields. HSV is similar to other color models such as HSL and HSB, but it defines color in slightly different ways.

In the HSV color model, Hue represents the dominant color or wavelength, and is usually measured in degrees on a color wheel from 0 to 360. Saturation refers to the purity or intensity of the color, and is usually measured as a percentage from 0% (gray or no color) to 100% (fully saturated color). Value (also sometimes called brightness) represents the overall intensity or lightness of the color, and is usually measured as a percentage from 0% (black) to 100% (white).

HSV is often used in computer programming and image processing to specify colors in various applications. By adjusting the values of Hue, Saturation, and Value, designers can create a wide range of colors and color schemes for use in various contexts.

For example, the HSV values for the color red are:

-   Hue: 0 or 360 (red is at the beginning and end of the hue spectrum)
-   Saturation: 100% (fully saturated)
-   Value: 100% (maximum brightness)

So the HSV representation of the color red would be hsv(0, 100%, 100%).

**Color wheel degrees**
The 12 major colors of the color wheel, at 30 degree intervals on the HSV (**hue, saturation, and value**)color wheel are the following: red (0 degrees or 360 degrees), orange (30 degrees), yellow (60 degrees), chartreuse green (90 degrees), green (120 degrees), spring green (150 degrees), cyan (180 degrees), azure (210 degrees)

![Color Degree ](https://c8.alamy.com/comp/H2KKW7/color-colors-wheel-names-degrees-rgb-H2KKW7.jpg)



Google introduces a new color system, called [HCT](https://github.com/material-foundation/material-color-utilities/blob/main/typescript/hct/hct.ts).  
HCT is short for:
Hue, ie the color in degrees (0..360)
Chroma, ie the colorfulness,and 
Tone, ie the lightness from white (100%)to black (0%).

For the color red, a possible HCT representation could be:

-   Hue: 0 or 360 (red is at the beginning and end of the hue spectrum)
-   Chroma: 100% (fully saturated)
-   Tone: around 50% (mid-range lightness, not too bright or too dark)

So a possible HCT representation of the color red could be hct(0, 100%, 50%). Please note that these values are just an approximation, and the specific HCT values used for the color red may differ depending on the context or application.