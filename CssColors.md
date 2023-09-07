# CSS3 Colors

## RGB Model

* There are two main color models: the additive RGB (red, green, blue) model used in electronic devices, and the subtractive CMYK (cyan, magenta, yellow, black) model used in print.

* Colors begin as black, and change as different levels of red, green, and blue are introduced. An easy way to see this is with the CSS rgb function.

* The CSS rgb function accepts values, or arguments, for red, green, and blue, and produces a color:  
  ~~~~
  rgb(red, green, blue);

* Each red, green, and blue value is a number from `0` to `255`. `0` means that there's 0% of that color, and is black. `255` means that there's 100% of that color.

* Secondary colors are the colors you get when you combine primary colors.  
  ~~~~
  /* Yellow */
  .one {
    background-color: rgb(255, 255, 0);
  }
  
  /* Cyan */
  .two {
    background-color: rgb(0, 255, 255);
  }
  
  /* Magenta */
  .three {
    background-color: rgb(255, 0, 255);
  }
  
  ~~~~

* Tertiary colors are created by combining a primary with a nearby secondary color.  All tertiary colors:
  ~~~~
  /* Orange */
  .one {
    background-color: rgb(255, 127, 0);
  }
  
  /* Spring green */
  .two {
    background-color: rgb(0, 255, 127);
  }
  
  /* Violet */
  .three {
    background-color: rgb(127, 0, 255);
  }
  ~~~~

  ~~~~
  /* Chartreuse green */
  .one {
    background-color: rgb(127, 255, 0);
  }
  
  /* Azure */
  .two {
    background-color: rgb(0, 127, 255);
  }
  
  /* Rose */
  .three {
    background-color: rgb(255, 0, 127);
  }
  ~~~~

* A color wheel is a circle where similar colors, or hues, are near each other, and different ones are further apart.

* Two colors that are opposite from each other on the color wheel are called complementary colors. If two complementary colors are combined, they produce gray. But when they are placed side-by-side, these colors produce strong visual contrast and appear brighter.  This contrast can be distracting if it's overused on a website, and can make text hard to read if it's placed on a complementary-colored background. **It's better practice** to choose one color as the dominant color, and use its complementary color as an accent to bring attention to certain content on the page.

## Hexadecimal Values

* A very common way to apply color to an element with CSS is with hexadecimal or hex values. Hex color values start with a `#` character and take six characters from 0-9 and A-F. The first pair of characters represent red, the second pair represent green, and the third pair represent blue.
* With hex colors, `00` is 0% of that color, and `FF` is 100%.

## HSL Color Model

* The HSL color model, or hue, saturation, and lightness, is another way to represent colors. The CSS hsl function accepts 3 values: a number from 0 to 360 for hue, a percentage from 0 to 100 for saturation, and a percentage from 0 to 100 for lightness.

![Color wheel](https://i.pinimg.com/1200x/16/f9/83/16f9837d960e7966da9ac68d6b76056c.jpg)

* In a color wheel, the hue red is at 0 degrees, green is at 120 degrees, and blue is at 240 degrees.
* Saturation is the intensity of a color from 0%, or gray, to 100% for pure color. You must add the percent sign `%` to the saturation and lightness values.
* Lightness is how bright a color appears, from 0%, or complete black, to 100%, complete white, with 50% being neutral.

## Color Transition and Gradient

* A gradient is when one color transitions into another. The CSS **`linear-gradient`** function lets you control the direction of the transition along a line, and which colors are used.  

  > One thing to remember is that the `linear-gradient` function actually creates an `image` element, and is usually paired with the `background` property which can accept an image as a value.
  >
  > While the `linear-gradient` function needs a minimum of two color arguments to work, it can accept many color arguments.
  >
  > ~~~~
  > .red {
  >   background: linear-gradient(90deg, rgb(255, 0, 0), rgb(0,255,0));
  > }
  > ~~~~
  >
  > 

* **Color-stops** allow you to fine-tune where colors are placed along the gradient line. They are a length unit like `px` or percentages that follow a color in the `linear-gradient` function. e.g. **75%** in below example, red takes up 75% of the marker:

  ~~~~
  .red {
    background: linear-gradient(90deg, rgb(255, 0, 0) 75%, rgb(0, 255, 0), rgb(0, 0, 255));
  }
  ~~~~

* If no `gradientDirection` argument is provided to the `linear-gradient` function, it arranges colors from top to bottom, or along a 180 degree line, by default.

## Opacity

* Opacity describes how opaque, or non-transparent, something is. With the value `0`, or 0%, the element will be completely transparent, and at `1.0`, or 100%, the element will be completely opaque like it is by default.

### Alpha Channel

* Another way to set the opacity for an element is with the alpha channel. Similar to the `opacity` property, the alpha channel controls how transparent or opaque a color is. The `rgba` function works just like the `rgb` function, but takes one more number from `0` to `1.0` for the alpha channel:  
  ~~~~
  .sleeve {
    background-color: rgba(255,255,255,50%)
  }
  ~~~~

* Alpha channel (CC added in ex.) in HEX:  (ex. #3B7E20**CC**)
  ~~~~
  .green {
    box-shadow: 0 0 20px 0 #3B7E20CC;
  }
  ~~~~

  

## Box Shadow

The `box-shadow` property lets you apply one or more shadows around an element.

~~~~
box-shadow: offsetX offsetY blurRadius spreadRadius color;
~~~~

* `blurRadius` and `spreadRadius` defaults to `0` if it isn't included.
* both `offsetX` and `offsetY` accept number values in `px` and other CSS units
* a positive `offsetX` value moves the shadow right and a negative value moves it left
* a positive `offsetY` value moves the shadow down and a negative value moves it up

The height and width of the shadow is determined by the height and width of the element it's applied to. You can also use an optional `spreadRadius` value to spread out the reach of the shadow.