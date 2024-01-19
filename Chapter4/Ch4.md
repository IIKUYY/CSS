## Pseudo-Classes and Pseudo-Elements

This two type of selectors, this ones acts on information about elements in or out the document tree.

- Pseudo-Classes: Differentiate between element's states or types, for example :hover, :visited, :active, etc.

- Pseudo-Elements: Grant access to different subparts of the element, for example, :first-line, :first-letter, etc.

This structures help to reduce the length of the code in order to achieve certain visual results

### Structural Pseudo-Classes

This pseudo-class is used to access to elements were simple selectors can't, for example in the next markup

```
<div>
<p>Lorem ipsum.</p>
<p>Dolor sit amet.</p>
</div>
```

Two elements ``<p>`` are child of the ``<div>`` element but the document tree doesn't provide any information that allows you to access to apply any rule, but, if you use the pseudo-class ``:first-child`` yo can

```
E:first-child {...}
```

#### The :nth-* Pseudo-classes

This one helps to find the position in an document tree, using numbers an the * character, this number can be modified in the same description using the letter n, for example, if you want to use a number, the doble of that number an then the triple, you can use this syntax

```
E:nth-*(n) {...}
E:nth-*(2n) {...}
E:nth-*(3n) {...}
```

you can also use operators like in the next example

```
E:nth-*(n+1) {...}
E:nth-*(2n+1) {...}
E:nth-*(3n-1) {...}
```

You can also use odds and even, and even numbers and 0

```
E:nth-*(even) {...}
E:nth-*(0n+3) {...}
E:nth-*(3) {...}
```

##### :nth-child() and nth-of-type()

This ones allows you to access to elements in a certain position based on the count of child in a parent element, and, in the count of elements of the same type, for example

```
E:nth-child(n) {...}
E:nth-of-type(n) {...}
```

This ones have the same rules as the ``:nth-*``

##### :nth-last-child() and :nth-last-of-type()

This ones act the same way as the previous ones, the core difference is that they count from bottom to top instead of from top to bottom, this serves if you want to make rules that begins in the last element of a kind

#### :first-of-type, :last-child, and :last-of-type

As their name implies, this selectors can access to elements based on their position in order of child and type, this ones only applies to one element so are useful to differentiate the first and last of a group of elements, like in this examples

```
tbody td:first-of-type { text-align: left; }
:first-child { text-decoration: underline; }
:last-child {font-style: italic; }
```

#### :only-child and :only-of-type

This selectors are used to select elements that have a parent but either no siblings or no siblings of the same type, like in this example

```
p:only-of-type { font-style: italic; }
p:only-child { text-decoration: underline; }
```

### Other Pseudo-Classes

This ones are some selectors that select elements based on other criteria like

#### :target

This one allows you to selects elements linked to an URI like in this markup

```
<h4 id="my_id">Lorem Ipsum</h4>
<a href="page.html#my_id">Lorem</a>
```

If you want to select the h4 when the URI is followed you can use the markup

```
#my_id:target {...}
```

#### :empty

This selector is useful when you want to select elements with no children, including text node, like in this example

```
<tr>
<td></td>
<td>Lorem ipsum</td>
<td><span></span><td>
```

if you apply 

```
td:empty {background-color: red;}
```

this rule only applies to the first td element

#### :root

This selector select the first element in a document tree, often the html element in html documents, you con use it like this

```
html {...} /*Specificity: 1; */
html:root {...} /*Specificity: 2; */
```

#### :not()

This selector is used to select elements that are different from the ones we specify, for example

```
div > :not(p) { color: red; }
```

#### UI Element States

Elements related to user inputs of forms can have different states, there are some selectors that act based on this state, like 

```
:checked {...}
:disable {...}
:enable {...}
```

There is a fourth state, indeterminate, this one is limited to some browser so don't have a clear markup

#### Constrain Validation Pseudo-Classes

The constrain validation, is a function that prevent a forms to be sent until somo requirements are met, this bring up some selectors like

```
:required {...}
:optional {...}
:valid {...}
:invalid {...}
:in-range {...}
:out-of-range {...}
```

The first two are useful to give style to some field if it is required or optional, The next two serves in case that the information provided in a fiel is a valid answer or not, and finally the last two are useful when a field offers a numeric option

### Pseudo-Elements

Like pseudo-classes this selectors allows you yo apply style to some of the elements, but this ones are more conceptual instead of using some kind of reference, there are four in CSS2 and they are

```
::first-line {...}
::first-letter {...}
::after {...}
::before {...}
```

#### The selection Pseudo-element

this pseudo-element let you stylize the element the user is selection in the page, like a text node, is written like this

```
::selection {...}
```

|                               | Chrome | Firefox | Safari |   IE |
| ----------------------------- | ------ | ------- | ------ | ---- |
|  Structural pseudo-classes    |   Yes  |    Yes  |   Yes  |  Yes |
| :target                       |   Yes  |    Yes  |   Yes  |  Yes |
| :empty                        |   Yes  |    Yes  |   Yes  |  Yes |
| :root                         |   Yes  |    Yes  |   Yes  |  Yes |
| :not()                        |   Yes  |    Yes  |   Yes  |  Yes |
| Pseudo-elements(:: syntax)    |   Yes  |    Yes  |   Yes  |  Yes |
| UI elements states            |   Yes  |    Yes  |   Yes  |  Yes |
| Constrain validation          |   Yes  |    Yes  |   Yes  | IE10 |
| ::selection                   |   Yes  |    Yes  |   Yes  |  Yes |

## [Prev](https://github.com/IIKUYY/CSS/tree/main/Chapter3/Ch3.md)
## [Index](https://github.com/IIKUYY/CSS/tree/main/index.md)
## [Next](https://github.com/IIKUYY/CSS/tree/main/Chapter5/Ch5.md)