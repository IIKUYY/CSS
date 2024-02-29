## Background Images

Adding decorative elements previous to CSS3 was tedious and difficult, but now at days there are much more options of personalization and properties aimed toward decorations

### Updates to Existing Background properties

Although adding new properties help, one of the backbones was to add more power and control to existing properties such as

#### background-position

The upgraded version of this property accept up to four values, side, length or percentage relative to a side, like this example

```
E { background-position: right 10em bottom 50%; }
```

In this syntax, the image will be 10em from the right and 50% from the bottom

#### background-attachment

This property accept three values, scroll (default) that makes the image doesn't scroll with the element but it will scroll with the viewport, fixed made the image doesn't scroll with neither viewport and element, and local that made the images moves with both viewport and element

#### background-repeat

In CCS2.1 there were four possible values in this property: no-repeat, repeat, repeat-x and repeat-y, in CSS3 there were added two properties, space that make the image repeats across the container as many times as possible without clipping, the images will be separated equally with the exceptions of the first one and the last one, and round that as well make the image repeats as many times as possible without clipping, but instead of equally spacing the repetitions, the image scales so a whole number of images fill the container

### Multiple Background images

The first new feature added, is that now, you can add more than one background image to a container, this is possible with the syntax

```
E { background-image: value, value; }
```

for each background layer you create, you can add appropriate values to all the background-* properties, there are two different ways to do this and this are

```
E {
  background-images: url('img1.svg'), url('img2.jpg');
  background-position: 95% 85%, 50% 50%;
  background-repeat: no-repeat;
}
```

Or

```
E {
  background:
  url('img1.svg') no-repeat 95% 85%;
  url('img2.jpg') no-repeat 50% 50%;
}
```

in case of using a color this one must be placed in the last instance of the comma separated list

### Dynamically Scaled Background images

A new property is background-size, the syntax is the next

```
E { background-size: value; }
```

the value can be, a pair of lengths, a pair of percentages, a single length or percentage, or a keyword, to make the image be it actual size use the keyword auto, if you only use one length the other will be consider auto, you can also use the multiple background with the this new property, a live example could be

```
E {
  background:
  url('img1.svg') no-repeat 95% 85%;
  url('img2.jpg') no-repeat 50% 80%;
  url('img3.jpg') no-repeat 10% 100%;
  url('img4.jpg') no-repeat 50% 50%;
  background-size: auto 80%, auto 15%, auto 50%, auto;
}
```

you can see that the size is applied in order, other two keywords are contain that scales the image to be the biggest as possible without exceeding the width and height of the container, and cover that scales the image to fit the large of the height or width, this make that the image will be cut in one of this values

### Background Clip and Origin

In CSS2 the position of a background image is define relative to the outer limit of its container padding, CSS3 added two properties, the first one is background-clip, this one sets the section of the box model that becomes the limit of where the background is displayed, the syntax is

```
E { background-clip: box; }
```
This box value can take one of three options, border-box (default) displays the background behind the border, content-box displays until the element padding and padding-box that displays the background until the border and not behind it, see in [Reference 1](https://github.com/IIKUYY/CSS/tree/main/Chapter8/Resorces/Reference 1.png)

The second property is background-origin this one lets you change the point where the background is calculated, the syntax is

```
E { background-origin: box; }
```

the box can have the same values as the background-clip, the explanation is the same but here is a visual example [Reference 2](https://github.com/IIKUYY/CSS/tree/main/Chapter8/Resorces/Reference 2.png)

### Upgraded Background Shortcut

This property was updated to include the new properties, the rules are the next, the background-size should follow the background-position and be separated with and slash, in the case of background-clip and background-origin, in case of one value this two have in common, this one will be set to the two properties, and in case of having two, the first one is set on background-origin, and the second one to background-clip

|                              | Chrome | Firefox | Safari |   IE |
| ---------------------------- | ------ | ------- | ------ | ---- |
| background-position (edge)   |   Yes  |    Yes  |   Yes  |  Yes |
| background-attachment        |   Yes  |    Yes  |   Yes  | IE10 |
| background-repeat (new)      |   Yes  |    No   |   No   |  Yes |
| background-repeat (two)      |   Yes  |    Yes  |   Yes  |  Yes |
| Multiple background images   |   Yes  |    Yes  |   Yes  | IE10 |
| background-size              |   Yes  |    Yes  |   Yes  |  Yes |
| Updated background property  |   Yes  |    Yes  |   Yes  |  Yes |
| background-clip              |   Yes  |    Yes  |   Yes  |  Yes |
| background-origin            |   Yes  |    Yes  |   Yes  |  Yes |


## [Prev](https://github.com/IIKUYY/CSS/tree/main/Chapter7/Ch7.md)
## [Index](https://github.com/IIKUYY/CSS/tree/main/index.md)
## [Next](https://github.com/IIKUYY/CSS/tree/main/Chapter9/Ch9.md)
