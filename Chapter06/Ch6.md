## Text Effects and Typographic Styles

Since the begging the text have being the backbone of the web, and in CSS3 a wave of new tools for Typography have been introduced

One of the most interesting additions, where the capability of adding shadows to text this allow to pretty good options of stylization for text, and for understanding how to use it first we need to learn one more thing

### Understanding Axes and Coordinates

CSS3 use a Cartesian Coordinates system, this is formed by two lines that cross each other in a 90 degree angle, the point of intersection is called origin, you can see an example in [Axes](https://github.com/IIKUYY/CSS/tree/main/Chapter6/Resorces/axes.png)

to use this, you need to use a pair of numbers, one describing the x-axis and describing the y-axis, to do this you declare first the x and then the y, you can see an example in [Coordinates](https://github.com/IIKUYY/CSS/tree/main/Chapter6/Resorces/coordinates.png)

### Applying Dimensional Effects: Text shadows

The syntax of adding shadows to a text is similar to this

```
E { text-shadow: x y color; }
```

This means the next, x and y refers to the position in which the shadows is seen, this having the text as origin, and the color is to clarify what color is the shadow

you need to have in mind to thinks, if you are familiar with Cartesian coordinates, you will note that the y axis is upside down, this is because the positive value for y project the shadow under the text, and with this information you can see that the values of x and y can be 0 and negative

#### Multiple shadows

You can add multiple shadows to a single text, the syntax looks like This

```
E { text-shadows: value, value, value; }
```

you can use it to make some cool effects that you can see in the example

### Restricting Overflow

Under certain circumstances you may need or want to limit the space the text use, via maintain it in a single line or in a certain width, you can use this function, witch syntax is the next

```
E{ text-overflow: keyword; }
```

the keywords are clip and ellipsis, the default value is clip, as it said in the name, it clips the characters in the point were the text overflow the container, the interesting one is ellipsis, this one function by replacing the last characters with a set of three point like this "(...)",

Also you can add a second keyword in the syntax, this is meant to modify the overflow at the beginning of the container, the first value modify the end and the second one modify the beginning

And the last option is to write a string of characters that would be used instead of the ellipse, the syntax of this are the next

```
E { text-overflow: ellipsis ellipsis; }
E { text-overflow: '~'; }
```

### Aligning text

The align text property have been around a long time, but in CSS3 its been added two new values, start and end, equivalent to left and right (respectively), the syntax is like This

```
E{ text-align-last: keyword; }
```

### Controlling Line Wrapping

A common issue in the use of dynamic text, is when the line wrapping is wrong, CSS3 gives you more control on how you want to manage this

#### Breaking Words

the first property is word-wrap, this one allows you to break long words in order to fit the container size, the syntax is like this

```
E{ word-wrap: keyword; }
```

#### Hyphenating Words

This functions add extra control, allowing you to determine where the break of the word will occur, the syntax is the next

```
E{ hyphens: keyword; }
```

this property allows three keyword, manual, where only happens where the author explicit said so in the markup with &shy, auto, where this happens where the browser determines if is necessary, and none where this does not happen

### Resizing Elements

Another useful property for elements larger than the container is the resizing, this function by give another size to the container, the syntax is the next

```
E{ resize: keyword; }
```

The keyword determine in witch direction the element can be dragged, horizontal, vertical, none and both

|                         | Chrome | Firefox | Safari |   IE |
| ----------------------- | ------ | ------- | ------ | ---- |
| text-shadow             |   Yes  |    Yes  |   Yes  | IE10 |
| text-overflow           |   Yes  |    Yes  |   Yes  |  Yes |
| text-align (New values) |   Yes  |    Yes  |   Yes  |  No  |
| text-align-last         |   Yes  |    Yes  |   No   |  Yes |
| overflow-wrap           |   Yes  |    Yes  |   Yes  |  Yes |
| hyphens                 |   No   |    Yes  |   Yes  | IE10 |
| resize                  |   Yes  |    Yes  |   Yes  |  No  |


## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter05/Ch5.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter06/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter07/Ch7.md)