## Introducing CSS3

In the first chapter were gonna see the bases of CSS3, first, we need to know that CSS3 is constantly changing, this happens overtime and between browser, for that reason is vital that you know the process of standardization.

### What CSS3 is and how it came to Be

First of all, the W3C approach to CSS3 is quite different to CSS2 so to understand we need to review the history.

#### A brief history of CSS3

The last mayor version was published in 1997, and recommended by the W3C in 2011, and this was the CSS2.1, IE was the first browser to use this version, but with the time others browsers came to be strong enough to be in the map, and some of this pack began to use CSS3, and with these, this version was target of changes towards the years by the community.

#### CSS3 is modular

To create a mark-up for every document is a titanic task, the W3C aware of that, to make the job easier, they divide CSS3 in various modules, each module be worked by different authors at different pace, for that reason you need to use CSS3 by modules and not like a monolith.

#### There is no CSS3

For the reasons enlisted before, theres no such a thing as a single CSS3 theres some parts of it, but no mark-up of everything.

### Module Status and the recommendation process

The term status, is some kind of labels use by the W3C to describe the progress of a module in the recommendation process, although is not a fair indication of the implementation of the module in the browsers.
The status are the following

*Working Draft* : This means that a document is published for the community to review it, this status may return if is necessary.

*Last Call* : This means that the review process is soon to be over, this indicate that the document is ready to advance into a new level.

*Candidate Recommendation* : At this point the document is basically accepted by the W3C, the technical requirements have been satisfied and the browser soon will be implementing it.

*Proposed Recommendation* : When two or more browsers implement the properties in the same way without technical issues the document gain this status.

*Recommendation* : Final step in which the W3C accept a document as part of the CSS3.

### Introducing the Syntax

To establish some kind of rules to make more easy the reading of the code the book use the next sintaxis

```
E { property : value; }
```

or for more values

```
E { property : first second third; }
```

### Vendor Prefixes

As we said earlier, some modules changes between browsers, in that case we can use prefixes as some kind value to make a general code, and will look like this

```
E {
    -prop-property : value; /* Firefox*/
    -pp-property : value; /*Internet Explorer*/
    -webkit-property : value; /*Chrome/Safari*/
}
```

## [Index](https://github.com/IIKUYY/CSS/tree/main/index.md)
## [Next](https://github.com/IIKUYY/CSS/tree/main/Chapter2/Ch2.md)