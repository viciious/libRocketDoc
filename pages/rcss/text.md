---
layout: page
title: Text
parent: rcss
---

### Alignment: the 'text-align' property

*text-align*

Value: | left \| right \| center
Initial: | left
Applies to: | block-level elements
Inherited: | yes
Percentages: | N/A

This property affects how inline boxes within a line box are aligned. Values have the following meanings:

left
>The row of inline boxes are aligned against the left edge of the line box. 

right
>The row of inline boxes are aligned against the right edge of the line box. 

center
>The row of inline boxes are aligned in the centre of the line box. 

Note that the 'justify' value is not yet supported in RCSS.

### Decoration

#### Underlining: the 'text-decoration' property

*text-decoration*

Value: | none \| underline
Initial: | none
Applies to: | all elements
Inherited: | yes
Percentages: | N/A

Values have the following meaning:

none
>Any text generated by this element has no additional decoration. 

underline
>Any text generated by this element has an underline, with a thickness and position specified by the font. 

The colour of any decoration is the same as the font colour. Note that 'overline' and 'line-through' is not yet supported in RCSS.

#### Text shadows: the 'shadow' font effect

Instead of using the CSS-standard 'text-shadow' property, text-shadowing is implemented in libRocket using the more generic font effect system. Below is an example of how to specify a shadow for an element of text.

```
/* Specify a grey text shadow on primary headings. */
h1
{
    darken-font-effect: shadow;
    darken-offset: 2px 2px;
    darken-color: grey;
}
```

### Whitespace: the 'white-space' property

*white-space*

Value: | normal \| pre \| nowrap \| pre-wrap \| pre-line
Initial: | normal
Applies to: | block-level elements
Inherited: | yes
Percentages: | N/A

This property defines how whitespace (any spaces, end-lines, carriage-returns and tabs) are processed in sections of text. Values have the following meanings:

normal
>Sequences of whitespace are collapsed down to single spaces. Lines are broken as necessary to fit line boxes. Line breaks in the source are ignored. 

pre
>Sequences of whitespace are preserved. Lines are only broken where line breaks are present in the source. 

nowrap
>Sequences of whitespace are collapsed. Lines are not broken. 

pre-wrap
>Sequences of whitespace are not collapsed. Lines are broken to fit line boxes or where line breaks are present in the source. 

pre-line
>Sequences of whitespace are collapsed. Lines are broken to fit line boxes or where line breaks are present in the source. 