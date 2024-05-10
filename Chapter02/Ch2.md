## Media Queries

Back in the world wide web era, the only to see websites was through laptops or desktops, now at days, there are plenty of ways to access, for that reasons, to write the CSS code, you need to think in the deferent kind of users you will have, for that reason CSS has had a way to serve different styles.

```
<link href="style.css" rel="stylesheet" media="screen">
```

But this approach isn´t perfect, in first instance the term "screen" is vague, it can be any kind of screen, the solution is use the media queries, this let you specify more the device, in order to customize more the code.
The Media queries module has a W3C recommendation, so is implemented in all major browser.

### The advantages of Media Queries

If you develop an a website for a computer, when a user try to access with a mobile device he might face some issues, some of them:

- Bad size of font and proportions.
- Unaccessible menus.
- Bigger images.
- etc.

The media queries solve some of this problems, from the start, they detect the device used via their attributes, with this, you can write each CSS for each device needs.

### Syntax

Thew media queries sets parameters to apply styles to different devices, you can use it in three ways.

The first one is with external style sheets.
```
<link href="file" rel="stylesheet" media="logic media and (expression)">
```

The second one is calling an external style sheet using the @import directive

```
@import url('file') logic media and (expression);
```

The third one is to use media queries in an embedded style element or in the style sheet itself with the extended @media rule:

```
@media logic media and (expression) { rules }
```

The last one is the one that be used in this document.

To begin with the syntax, the media attribute declares the media type that the styles are applied to, like this.

```
<link href="style.css" rel="stylesheet" media="screen">
```

The most common media types are screen and print, in case you are writing rules for all the types, this examples are equally useful.

```
@media all and (expression) { rules }
@media (expression) { rules }
```

The next attribute is logic, this optional rule can have two values "only" or "not".

```
@media only media and (expression) { rules }
@media not media and (expression) { rules }
```

Only is used if you want to hide the rule from older browsers that don´t support the syntax.
Not is used when you want the rule to be applied when the parameters are not met.
If you use logic or media, you have to use the and operator.

### Media Features

this are the information about the device, dimension, resolution, etc. this information evaluate the expression, the result determine the rule to be applied.
In media queries, most of the expressions require that a value be supplied:

```
@media (feature: value) { rules }
```

lets see some features

#### Width and Height

This specify the size of the screen and the basic syntax use length values

```
@media (width: 600px) { rules }
```

it can be used with different values, and using max and min to make limits to the rules

```
@media (width: 300px) { rules }
@media (max-width: 480px) { rules }
@media (min-width: 640px) { rules }
```

#### Pixel ratio

In general the screen of any device can be measure with pixel, this unit instead of describe the size, describe the resolution of the device, but the px translate to 4 real pixels.
As the width and height, this value con be use with max and min.

```
@media (max-resolution: 1.5dppx) { rules }
```

Some browser don´t read this, for this reason you need to use some other kind of unit beside dppx, for IE you use the dpi, that is the dppx multiplied by 96, and for safari you need to use -webkit-device-pixel-ratio, a example code is.

```
@media (resolution: 1.5dppx), (resolution: 144dpi), (-webkit-device-pixel-ratio: 2) { rules }
```

#### Device width and height

the width and height refers to the browser viewport, and not to the actual device screen size, and this value is measured in CSS pixels, to make used of this feature you use the tag viewport, like in this example

```
<meta name="viewport" content="width=device-width">
```

#### Orientation

The orientation is the feature that read the position of the device typically vertical or horizontal, the syntax is the following

```
@media (orientation: value) { rules }
```

the value is one of two

- Portrait: width < height
- Landscape: height < width

#### Aspect Ratio

you can also create queries that triggers when certain ratio between width and height is met, here is the syntax

```
@media (aspect-ratio: horizontal/vertical) { rules }
@media (device-aspect-ratio: horizontal/vertical) { rules }
```

it can be write in this form 16/9

#### Chains

You can chain queries like this

```
@media logic media and (expression) and (expression) { rules }
```

### Mobile-First web development

A  now common practice in web development is to design the page first for smaller screens to then ad assets to support bigger ones, this is used because some browser loads the assets first and then check the queries, this is useful when you create the page for the least powerful devices and then for the most powerful ones.

### Media queries support

|         | Chrome | Firefox | Safari |  IE |
| ------- | ------ | ------- | ------ | --- |
| Queries |   Yes  |    Yes  |   Yes  | Yes |


## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter01/Ch1.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter02/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter03/Ch3.md)