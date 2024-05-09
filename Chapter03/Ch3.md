## Selectors

The selectors are the core of CSS, this can be divided into two categories, the ones that act directly on elements defined in the document tree, this can be named DOM selectors, en the second are the pseudo-selectors that acto on elements outside the document tree, in this chapter we see thew DOM selectors.

### Attribute selector

Introduced in CSS2, this selectors allow you to specify rules that match elements based on their attribute, the four selectors specified are:

```
E[attr] {...} /* Simple Attribute Selector */
E[attr='value'] {...} /* Exact Attribute Value Selector */
E[attr~='value'] {...} /* Partial Attribute Value Selector */
E[attr|='value'] {...} /* Language Attribute Selector */
```

we will see how to use this ones quickly, for that we use this list of contacts

```
<ul>
<li><a href="" lang="en-GB" rel="friend met">Peter</a></li>
<li><a href="" lang="es-ES" rel="friend">Pedro</a></li>
<li><a href="" lang="es-MX" rel="contact">Pancho</a></li>
</ul>
```

The Simple Attribute Selector applies rules to elements that have the specified attribute, so we can use it like this, this make all the rel color red

```
a[rel] { color:red; }
```

The Exact Attribute Value Selector applies rules to elements with a specific value in the attribute, like this example were you make red all the friends list

```
a[rel='friend'] { color:red; }
```

The Partial Attribute Value Selector applies rules to elements with a certain range of precision in the value, like this example that make all elements with values similar to friends red

```
a[rel~='friend'] { color:red; }
```

The Language Attribute Selector applies rules to elements with the language specified and that match the selector, like this example were the elements in Spanish turn red

```
a[lang|='es] { color:red; }
```

### New Attribute selector in CSS3

Beginning Substring Attribute Value Selector or the Beginning Selector select the elements that begin their argument with the string provided 

```
E[attr^=''] {...}
```

like in this case, with the list provided

```
<li><a href="http://example.com/"title="Image Library">Example</a><li>
<li><a href="http://example.com/"title="Free Image Library">Example<a href=></li>
<li><a href="http://example.com/"title="Free Sound Library">Example</a></li>
```

Where when we use the next selector we applies the rule only to the first element

```
a[title^='image'] {...}
```

This selector is specially useful when you want to add visual information to your hyperlinks

The Ending Substring Attribute Value Selector or the ending selector, function like the beginning selector but for the end of the argument and is used like this

```
E[attr$='value'] {...}
```

The Arbitrary Substring Attribute Value Selector or the Arbitrary Selector this like the other two search for an string, but the difference is that it can be in any part of the argument

```
E[attr*='value'] {...}
```

#### Multiple Attribute Selectors

You can chain selectors to apply multiples rules tied to each other like in this example, in this case there are two document in two different folders

```
<p><a href="http://example.com/folder1/file.pdf">Example</a></p>
<p><a href="http://example.com/folder2/file.pdf">Example</a></p>
```

If you can applies some rules to the second folder you can chain it like this

```
a[href^='http://'][href*='/folder2/'][href$='.pdf']{...}
```

### The General Sibling Combinator

The last DOM selector is a combinator, witch means that joins more than one selector this one is similar to the Adjacent Sibling Combinator

```
E+F{...} /* Adjacent Sibling Combinator */
E~F{...} /* General Sibling Combinator */
```

the key difference is that  while the adjacent combinator only selects elements immediately preceded by the element (E), the general combinator can select any (F) that is preceded by element (E) on the same level of the tree.

|                    | Chrome | Firefox | Safari |  IE |
| ------------------ | ------ | ------- | ------ | --- |
|  New attributes    |   Yes  |    Yes  |   Yes  | Yes |
| General combinator |   Yes  |    Yes  |   Yes  | Yes |

## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter02/Ch2.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter03/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter04/Ch4.md)