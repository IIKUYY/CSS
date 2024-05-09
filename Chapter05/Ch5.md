## Fonts

The fonts are one of the oldest features in CSS so there are some of them and pretty much options to personalice it

### The @font-face rule

To display fonts, you first need to define it by using this rule, this one looks like this

```
@font-face {
    font-family: FontName;
    src: local('fontname'), url:('/pathfilename.otf') format('opentype');
}
```

A example using a real font is teh following

```
@font-face {
    font-family: ChunkFive;
    src: local('ChunkFive'), url('ChunkFive.woff') format('woff');
}
h1.webfont { font-family: ChunkFive, sans-serif; }
```

in the font family property, we declare the name of the font, the src tell the browser the location of the file, local search in the users machine if the font is already installed, url provides a path if the font isn't locally, and format specify the font type.

#### Defining different faces

The previous ways to define fonts is a great one, but only define one face, if you want to define more faces, you want to add more lines, like this

```
@font-face {
    font-family: 'Gentium Basic';
    src: url ('GenBasR.woff') format('woff');
}
@font-face {
    font-family: 'Gentium Basic';
    font-style: italic;
    src: url ('GenBasR.woff') format('woff');
}
h1{ font-family: 'Gentium Basic', sans-serif; }
```

You make two profiles, one for the basic and one for the italic one, tho only thing yo use it is the tag ``<em>``.

#### True vs Artificial Font faces


If you want to define a face for a font you need to use a link or the browser will try to recreate it but surely it would do a bad work.

### A "Bulletproof" @font-face syntax

This rule is being since 1997 so you need to work around the legacy and the errors, and all the things that being happening since then, so here is a series of problems and how to address it.

#### Using local fonts

the local value check if the user already has the defined font, but this have some issues, the first one is that local is not supported by IE below to 9, other issue is that some font managers does not work good with local, so leaving out his function tend to be safer

#### Font formats 

Originally in IE 8 and below, the only format that was supported was  Microsoft’s proprietary Embedded OpenType (EOT), so in recent times the most common type of font used is the one that Mozilla created, the Web open font format (woff) that is supported in all mayor browsers, and for mobile use, is common to uses Sealable Vector Graphics (vsg).

#### Syntax Example

A final bulletproof example can be

```
@font-face {
    font-family: 'Gentium Basic' ;
    src: url ('GenBkBasR.eot') ;
    src: url ('GenBasR.eot?#iefix') format ('embedded-opentype') ;
    url ('GenBkBasR.woff') format ('woff') ;
    url ('GenBkBasR.tff') format ('truetype') ;
```

this syntax, define the family, give a lint to IE8 and below EOT, give a WOFF for newer browsers and a TFF for older android browser, for best compatibility you can use @font-face generator by Font Squirrel (http://www.fontsquirrel.com/fontface/generator/)

### Licensing Fonts for web use

You cant use any font in your web, some of them are protected by their creators, so before you use some font, you need to check if is legally to use it, some font providers created mechanism that allows you to embed fonts legally using JavaScript, the provider is authorized to serve the font files so, you can call font families in your stacks, this method is called Fonts as Service (FaaS)

### A Real-World Fonts example

This is a example of a CSS document for fonts, in this case is simplified to a single format, but in a real case you need to add the various formats as show before

```
@font-face {
    font-family: 'CartoonistHand';
    src: url ('CartoonistHand.woff') format ('woof');
}
@font-face {
    font-family: 'CartoonistHand';
    font-style: italic;
    src: url ('CartoonistHand-Italic.woff') format ('woof');
}
@font-face {
    font-family: 'CartoonistHand';
    font-style: bold;
    src: url ('CartoonistHand-Bold.woff') format ('woof');
}
@font-face {
    font-family: 'ChunkFiveRegular';
    src: url ('Chunkfive.woff') format ('woof');
}
@font-face {
    font-family: 'AirstreamRegular';
    src: url ('Airstream.woff') format ('woof');
}
.font-face h1 { font-family: ChunkFiveRegular, sans-serif; }
.font-face h2 { font-family: AirstreamRegular, cursive; }
.font-face p { font-family: CartoonistHand, sans-serif; }
```

this define three families and declares in witch syntaxes is used

### Controlling Fonts Loading

Web fonts are loaded as external assets, so, in some cases the font will load later than the text, in this cases thw font will change in a flash after this one is loaded, if you use FaaS providers, some ones have ways to work around this problems, but if you host your own fonts, you should check Web Fonts Loader Library in (https://github.com/typekit/webfontloader/)


### More Fonts Properties

CSS3 revives two fonts properties proposed for CSS2, this ones are

#### font-size-adjust

You can change the size of a font in different cases, this function if in the stack there are some drastic changes in size and in some cases become difficult to read a disproportional text, so you can use this syntax

```
E { font-size-adjust: number; }
```

Where E is the case where the rule is applied, and number is a proportional change, for example, if the original font is 16 px, if you use 0.5, the value of the height of this adjust will be 8px, a example is 

```
h1.adjust { font-size-adjust: 0.517; }
```

A problem of this method is that you need to manually calculate the number you have to use to have the size you want, and for this, you need to know the size of the original font

#### font-stretch

Some fonts families have condensed or expanded variants, this property allows you to access this ones the syntax is

```
E { font-stretch: keyword; }
```

The keyword can be: normal, ultra-condensed, extra-condensed, condensed, semi-condensed, and the same prefixes but for expanded, a example can be

```
h1 { font-family: 'PT Sans', sans-serif; }
h1.narrow { font-stretch: condensed; }
```

You can replicate this property in the browser that don't support it by using the @font-face like this

```
@font-face {
    font-family: 'PT Sans Condensed';
    src: url('PT-Sans-Narrow.woff') format('woff'):
}
```

### OpenType Features

CSS3 font features are limited compered with other applications, so you can do other kind of stuff beside CSS3 normal markup

#### Enabling Font Features

Browsers have implemented a property that allows you to explore the extra features, this is called font-features-settings, this is the syntax

```
E { font-feature-settings: "parameters", "parameters" on/off; }
```

in place of parameters you write a string of characters that are assign to one feature

Here is a live example

```
.smallcaps { font-variant: small-caps; }
.ot-smallcaps { font-features-settings: "smcp"; }
```

#### Font Features Properties

The individual features you enable or disable in by font-feature-settings are also specified to be implemented as individual properties known as font-variants, this is a example

```
E { font-variant-ligatures: no-discretionary-ligatures; }
```

you can also modified position with values as super or subscript or kerning

|                       | Chrome | Firefox | Safari |   IE |
| --------------------- | ------ | ------- | ------ | ---- |
|  @font-face           |   Yes  |    Yes  |   Yes  |  Yes |
| font-size-adjust      |   No   |    Yes  |   No   |  No  |
| font-stretch          |   No   |    Yes  |   No   |  Yes |
| font-feature-settings |   Yes  |    Yes  |   No   | IE10 |
| font-variant-*        |   Yes  |    No   |   Yes  |  No  |


## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter04/Ch4.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter05/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter06/Ch6.md)