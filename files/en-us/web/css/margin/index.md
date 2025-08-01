---
title: margin
slug: Web/CSS/margin
page-type: css-shorthand-property
browser-compat: css.properties.margin
sidebar: cssref
---

The **`margin`** [CSS](/en-US/docs/Web/CSS) shorthand property sets the [margin area](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#margin_area) on all four sides of an element.

{{InteractiveExample("CSS Demo: margin")}}

```css interactive-example-choice
margin: 1em;
```

```css interactive-example-choice
margin: 5% 0;
```

```css interactive-example-choice
margin: 10px 50px 20px;
```

```css interactive-example-choice
margin: 10px 50px 20px 0;
```

```css interactive-example-choice
margin: 0;
```

```html interactive-example
<section id="default-example">
  <div id="container">
    <div class="row"></div>
    <div class="row transition-all" id="example-element"></div>
    <div class="row"></div>
  </div>
</section>
```

```css interactive-example
#container {
  width: 300px;
  height: 200px;
  display: flex;
  align-content: flex-start;
  flex-direction: column;
  justify-content: flex-start;
}

.row {
  height: 33.33%;
  display: inline-block;
  border: solid #ce7777 10px;
  background-color: #2b3a55;
  flex-shrink: 0;
}

#example-element {
  border: solid 10px #ffbf00;
  background-color: #2b3a55;
}
```

## Constituent properties

This property is a shorthand for the following CSS properties:

- {{cssxref("margin-top")}}
- {{cssxref("margin-right")}}
- {{cssxref("margin-bottom")}}
- {{cssxref("margin-left")}}

## Syntax

```css
/* apply to all four sides */
margin: 1em;
margin: -3px;

/* top and bottom | left and right */
margin: 5% auto;

/* top | left and right | bottom */
margin: 1em auto 2em;

/* top | right | bottom | left */
margin: 2px 1em 0 auto;

/* anchor-size() values */
margin: 5% anchor-size(width);
margin: calc(anchor-size(width) / 4) 1em 0
  anchor-size(--myAnchor self-inline, 50px);

/* Keyword values */
margin: auto;

/* Global values */
margin: inherit;
margin: initial;
margin: revert;
margin: revert-layer;
margin: unset;
```

The `margin` property may be specified using one, two, three, or four values. Each value is a {{cssxref("&lt;length&gt;")}}, a {{cssxref("&lt;percentage&gt;")}}, or the keyword `auto`. Negative values draw the element closer to its neighbors than it would be by default.

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

- {{cssxref("length")}}
  - : The size of the margin as a fixed value.
    - For _anchor-positioned elements_, the {{cssxref("anchor-size()")}} function resolves to a {{cssxref("&lt;length&gt;")}} value relative to the associated _anchor element_'s width or height (see [Setting element margin based on anchor size](/en-US/docs/Web/CSS/CSS_anchor_positioning/Using#setting_element_margin_based_on_anchor_size)).

- {{cssxref("percentage")}}
  - : The size of the margin as a percentage, relative to the inline size (_width_ in a horizontal language, defined by {{cssxref("writing-mode")}}) of the [containing block](/en-US/docs/Web/CSS/CSS_display/Containing_block).
- `auto`
  - : The browser selects a suitable margin to use. For example, in certain cases this value can be used to center an element.

## Description

This property can be used to set a margin on all four sides of an element. Margins create extra space _around_ an element, unlike {{cssxref("padding")}}, which creates extra space _within_ an element.

The top and bottom margins have no effect on _non-[replaced](/en-US/docs/Glossary/Replaced_elements)_ inline elements, such as {{HTMLElement("span")}} or {{HTMLElement("code")}}.

### Horizontal centering

You can horizontally center an element within its parent by setting `margin: 0 auto;`.

A more common method to center an element horizontally is by setting `display: flex;` and [`justify-content: center;`](/en-US/docs/Web/CSS/justify-content) on a container, which [centers its flex item](/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container) children.

### Margin collapsing

Elements' top and bottom margins are sometimes collapsed into a single margin that is equal to the larger of the two margins. See [Mastering margin collapsing](/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing) for more information.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Basic example

#### HTML

```html
<div class="center">This element is centered.</div>

<div class="outside">This element is positioned outside of its container.</div>
```

#### CSS

```css
.center {
  margin: auto;
  background: lime;
  width: 66%;
}

.outside {
  margin: 3rem 0 0 -3rem;
  background: cyan;
  width: 66%;
}
```

{{ EmbedLiveSample('Basic_example','100%',120) }}

### More examples

```css
margin: 5%; /* All sides: 5% margin */

margin: 10px; /* All sides: 10px margin */

margin: 1.6em 20px; /* top and bottom: 1.6em margin */
/* left and right: 20px margin */

margin: 10px 3% -1em; /* top:            10px margin */
/* left and right: 3% margin   */
/* bottom:         -1em margin */

margin: 10px 3px 30px 5px; /* top:    10px margin */
/* right:  3px margin  */
/* bottom: 30px margin */
/* left:   5px margin  */

margin: 2em auto; /* top and bottom: 2em margin   */
/* Box is horizontally centered */

margin: auto; /* top and bottom: 0 margin     */
/* Box is horizontally centered */
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("margin-top")}}, {{cssxref("margin-right")}}, {{cssxref("margin-bottom")}}, and {{cssxref("margin-left")}}
- {{cssxref("margin-block-start")}}, {{cssxref("margin-block-end")}}, {{cssxref("margin-inline-start")}}, and {{cssxref("margin-inline-end")}}
- {{cssxref("margin-block")}} and {{cssxref("margin-inline")}} shorthands
- [Mastering margin collapsing](/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)
- [Introduction to the CSS box model](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) guide
- [CSS box model](/en-US/docs/Web/CSS/CSS_box_model) module
