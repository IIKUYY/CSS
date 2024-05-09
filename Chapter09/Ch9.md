## Border and Box Effects

Perhaps the ability to give borders to elements have since CSS1, the markup to give some common round end or shadow were pretty complicated, and in CSS3 we have more ways to work around this issues

### Giving your Borders Rounder Corners

In the beginning of web design, in order to add a round corner to an object you have to add four images an at least two extra nonsemantic elements, now with the new CSS3 elements, we can make this with only CSS code, first we need to now that each corner is treated as a quarter of ellipse, that you can modify with this syntax

```
E { border-v-h-radius: x y; }
```

In this example v substitute the value of top or bottom and h the value of left and right, x and y do the same for numeric values of each coordinate, an live example can be

```
div { border-top-right-radius: 20px 20px; }
```

if you want to have x and y the same size you only need to write the size of both once and it would recognize it

#### The border-radius shorthand

A shorthand in order to not write the size of each corner radius is to use this syntax

```
E { border-radius: [top-left] [top-right] [bottom-right] [bottom-left]; }
E { border-radius: [top-left] [top-right and bottom-left] [bottom-right]; }
E { border-radius: [top-left and bottom-right] [top-right and bottom-left]; }
E { border-radius: [top-left and top-right and bottom-right and bottom-left]; }
```

Each case applies in the number of number you gave to the values of x and y, in case of this shorthand, only works for regular corners, so only one number per value

The shorthand for irregular curves is the next

```
E { border-radius: horizontal-radius/vertical-radius; }
```

this follow the same rules as the regular one, but adding the ability to make irregular Corners

#### Using Percentage values

The previous examples use length values, but you can also make use of percentage values like this

```
div {
  border-radius: 50%;
  height: 100px;
}
.ellipse { width: 200px; }
.circle { width: 100px; }
```

### Using images as borders

The main objective of giving borders to elements is esthetic, so you can make use of images

#### border-image-source

This property allows you to add some image to your border, the syntax is

```
E { border-image-source: url('something.png'); }
```

#### border-image-slice

Once you have the source of the border you have to slice it, this property accept between one of four values each one of this refers to one side of an elements similar to border-radius this values are used to set a distance from each edge of the image, marking the area used to "frame" the element let explain with an examples

```
E { border-image-slice: 34; }
```

 note that there are no units this is for two purposes, for bitmaps images that uses pixel values, and for vector images that uses coordinate values, or you can use percentages as substitute, this value dictate from what point from top left bottom or right the border start

 the default behavior of border images is to only the slices and corners on the border, leaving the center of the element blank for its own background properties, the border-image-slice has a property of value fill, when you use this the area of image inside the slices will be applied over the background of the element in the appropriate place

#### border-image-width

border-image-slice stretch or condense the image to fit the width of the element's border, you can modify this value by using

```
E { border-image-width: value; }
```

like border-width or border-image-slice the value can be up to four to match the sides, each of this can be unitless, length or percentage, unless border-width, this property does not affect the layout of the page,

#### border-image-outset

By default, a border image starts displaying from the outside of the border box, moving in toward the content box, yo can change this behavior by out setting the image to start from outside the border box, for example, to outset the border image by 10px from the top and bottom, and 5px from left and right, you use this syntax

```
E { border-image-outset: 15px 30px; }
```

#### border-image-repeat

This property control how the image fits the length of each side between the corners

```
E { border-image-repeat: keyword; }
```

the keywords accepted are three, stretch (default), repeat and round, to understand this in a faster and better way you can se the [Example](https://github.com/IIKUYY/CSS/tree/main/Chapter9/Resorces/Reference.png)

You can use two of this keyword, one for the vertical value and one for the horizontal value, the first control the horizontal and the second the vertical

#### The border-image Shorthand property

The syntax looks like this

```
E { border-image: source slice / width / outset repeat; }
```

### Drop Shadows

You can add shadows to box elements with a similar syntax to text-shadows, and is

```
E { box-shadow: inset horizontal vertical blur-radius spread color; }
```

inset is an optional keyword that sets the shadow outside or inside the box, the horizontal and vertical values as in text-shadows set the distance of the shadow in relation of the element, blur radius as well work like in text-shadows, spread sets the distance the shadow spread and color set the color of the shadow

### Inset Shadows

This option as mention in the previous section set the shadow inside the box of the element instead of outside, but it also flip the shadow like a mirror in the diagonal of the rectangle, if you have a x positive y positive shadow, it normally shows bottom right, but in the inside it shows in top left

|                   | Chrome | Firefox | Safari |   IE |
| ----------------- | ------ | ------- | ------ | ---- |
| border-radius     |   Yes  |    Yes  |   Yes  |  Yes |
| border-image      |   Yes  |    Yes  |   Yes  | IE11 |
| border-shadow     |   Yes  |    Yes  |   Yes  |  Yes |


## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter08/Ch8.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter09/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter10/Ch10md)