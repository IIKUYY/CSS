## Multiple Columns

Although desktops screens have gotten wider and wider people are not comfortable reading longer lines of text, this lead to some conventions in the design of web pages

In other areas like magazines and newspapers, the design tackle this problems with the use of multiple columns, and thankfully in CSS3 there is a layout module that allows to do multiple columns

### Column Layout Methods

You can divide your content into columns using two methods, prescriptively, you deciding in advance the number of columns or either dynamically, making the browser calculate the number of columns that fits the device with a fix width

#### Prescriptively Columns: column-count

The syntax is the next

```
E { column-count: columns; }
```

The element E is the parent that we want to divide and in columns we set the number of columns we want

#### Dynamic Columns: column-width

The second method syntax is

```
E { column-width: length; }
```

The element E is the parent that we want to divide and in length we set the width of the columns

#### Varying Distribution of Content Across columns

By default, the content is distributed equally among all the columns, in case that this is not possible, the browser will make the last column the shortest

you can manipulate this fixes with the syntax

```
E { column-fill: keyword; }
```

Were keyword can take two values, balance, that tries to make all columns equal, and auto that fill the columns sequentially, this function only work if the parent element has fixed height, in this case the content will continue until reach the end of the height and then continue to the next columns

#### Combining column-count and column-width

In case you use both properties in the same element, the column-count will act as a maximum number of columns that the element can have, here is a syntax using both properties in the same line

```
E { columns: column-width column-count; }
```

in a live example

```
div { columns: 150px 3; }
```

### Column Gaps and Rules

When using a prescriptive multi-column layout, the browser should place a default 1em gap between each column, however, you can alter this value by using the syntax

```
E { column-gap: length; }
```

were you can change the separation of each column using the em unit, as well you can use other syntax to add a border that visually limits the column, this is

```
E {
  column-rule-width: length;
  column-rule-style: border-style;
  column-rule-color: color;
  column-rule: length border-style color;
}
```
using this properties you can vary the length, style and color of this line

### Contain elements within Columns

If place an element with greater width than a column in this syntax, the element will be cut in a halfway point in the gap

### Elements Spanning Multiple columns

Sometimes you want an element break the flow in the columns, like a subtitle or a section divider, in this cases we use this syntax

```
E { column-span: value; }
```

the value only can be one of two, all or none, the default is none were the element will be part of the columns, in the all variant, the content before the element and the content after it will be separated in columns, but the specified element will not

|                | Chrome | Firefox | Safari |   IE |
| -------------- | ------ | ------- | ------ | ---- |
| column-count   |   Yes  |    Yes  |   Yes  | IE10 |
| column-width   |   Yes  |    Yes  |   Yes  | IE10 |
| columns        |   Yes  |    Yes  |   Yes  | IE10 |
| column-fill    |   No   |    Yes  |   No   | IE10 |
| column-gap     |   Yes  |    Yes  |   Yes  | IE10 |
| column-rule    |   Yes  |    Yes  |   Yes  | IE10 |
| column-span    |   Yes  |    No   |   Yes  | IE10 |


## [Prev](https://github.com/IIKUYY/CSS/blob/main/Chapter06/Ch6.md)
## [Index](https://github.com/IIKUYY/CSS/blob/main/Chapter07/README.md)
## [Next](https://github.com/IIKUYY/CSS/blob/main/Chapter08/Ch8md)