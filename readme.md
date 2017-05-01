[![Build Status](https://travis-ci.org/marcobiedermann/css-style-guide.svg?branch=master)](https://travis-ci.org/marcobiedermann/css-style-guide)
[![devDependency Status](https://david-dm.org/marcobiedermann/css-style-guide/dev-status.svg)](https://david-dm.org/marcobiedermann/css-style-guide#info=devDependencies)

# CSS Style Guide

A style guide which helps you write better, performant, structured, scalable and maintainable CSS.

## Table of contents

* [CSS](#css)
	* [Color](#color)
	* [Font](#font)
	* [Number](#number)
	* [String](#string)
	* [Length](#length)
	* [Time](#time)
	* [Unit](#unit)
	* [Value](#value)
	* [Value list](#value-list)
	* [Shorthand property](#shorthand-property)
	* [Property](#property)
	* [Keyframe declaration](#keyframe-declaration)
	* [Declaration](#declaration)
	* [Selector list](#selector-list)
	* [Rule](#rule)
	* [Media query list](#media-query-list)
	* [Comment](#comment)

## CSS

### Color

Color must be written in lowercase.

Bad

```css
body {
  color: #FFF;
}
```

Good

```css
body {
  color: #fff;
}
```

Stylelint: [`color-hex-case`](https://stylelint.io/user-guide/rules/color-hex-case/)

---

Color must be witten with shorthand notation.

Bad

```css
body {
  color: #ffffff;
}
```

Good

```css
body {
  color: #fff;
}
```

Stylelint: [`color-hex-length`](https://stylelint.io/user-guide/rules/color-hex-length/)

---

Color names must be avoided.

Bad

```css
body {
  color: white;
}
```

Good

```css
body {
  color: #fff;
}
```

Stylelint: [`color-named`](https://stylelint.io/user-guide/rules/color-named/)

### Font

Quotes are required around font-family names when they are not valid CSS identifiers.

Bad

```css
body {
  font-family: Open Sans;
}
```

Good

```css
body {
  font-family: 'Open Sans';
}
```

Stylelint: [`font-family-name-quotes`](https://stylelint.io/user-guide/rules/font-family-name-quotes/)

---

Font-weight notation must be written in numeric value.

Bad

```css
body {
  font-weight: bold;
}
```

Good

```css
body {
  font-weight: 700;
}
```

Stylelint: [`font-weight-notation`](https://stylelint.io/user-guide/rules/font-weight-notation/)

### Number

Fractal number must always have a leading zero.

Bad

```css
body {
  font-size: .875rem;
}
```

Good

```css
body {
  font-size: 0.875rem;
}
```

Stylelint: [`number-leading-zero`](https://stylelint.io/user-guide/rules/number-leading-zero/)

---

Number decimal precision must be limited to three.

Bad

```css
.column {
  width: 66.6667%;
}
```

Good

```css
.column {
  width: 66.667%;
}
```

Stylelint: [`number-max-precision`](https://stylelint.io/user-guide/rules/number-max-precision/)

---

Number must not have a trailing zero.

Bad

```css
.body {
  font-size: 1.0rem;
}
```

Good

```css
.body {
  font-size: 1rem;
}
```

Stylelint: [`number-no-trailing-zeros`](https://stylelint.io/user-guide/rules/number-no-trailing-zeros/)

### String

Strings must always be wrapped with single quotes.

Bad

```css
.body {
  font-family: "Open Sans";
}
```

Good

```css
.body {
  font-family: 'Open Sans';
}
```

Stylelint: [`string-quotes`](https://stylelint.io/user-guide/rules/string-quotes/)

### Length

Number with zero length must not have units.

Bad

```css
body {
  margin: 0px;
}
```

Good

```css
body {
  margin: 0;
}
```

Stylelint: [`length-zero-no-unit`](https://stylelint.io/user-guide/rules/length-zero-no-unit/)

### Time

Mininum number of milliseconds for time values must be at least 100.

Bad

```css
a {
  transition: color 80ms;
}
```

Good

```css
a {
  transition: color 100ms;
}
```

Stylelint: [`time-min-milliseconds`](https://stylelint.io/user-guide/rules/time-min-milliseconds/)

### Unit

Unit value must be written in lowercase.

Bad

```css
body {
  margin: 10PX;
}
```

Good

```css
body {
  margin: 10px;
}
```

Stylelint: [`unit-case`](https://stylelint.io/user-guide/rules/unit-case/)

### Value

Keyword values must be written in lowercase.

Bad

```css
body {
  display: FLEX;
}
```

Good

```css
body {
  display: flex;
}
```

Stylelint: [`value-keyword-case`](https://stylelint.io/user-guide/rules/value-keyword-case/)

---

Vender prefixes must not be used. Use [Autoprefixer](https://github.com/postcss/autoprefixer) to add them depending on browser support.

Bad

```css
body {
  display: -ms-flexbox;
  display: flex;
}
```

Good

```css
body {
  display: flex;
}
```

Stylelint: [`value-no-vendor-prefix`](https://stylelint.io/user-guide/rules/value-no-vendor-prefix/)

### Value list

Values must never have space before commans and must always have space after comma.

Bad

```css
body {
  background-size: 50% ,50%;
}
```

Good

```css
body {
  background-size: 50%, 50%;
}
```

Stylelint: [`value-list-comma-space-after`](https://stylelint.io/user-guide/rules/value-list-comma-space-after/), [`value-list-comma-space-before`](https://stylelint.io/user-guide/rules/value-list-comma-space-before/)

---

Bad

Values must always be written in single line.

```css
body {
  background-size: 50%,
                   50%;
}
```

Good

```css
body {
  background-size: 50%, 50%;
}
```

Stylelint: [`value-list-comma-newline-after`](https://stylelint.io/user-guide/rules/value-list-comma-newline-after/), [`value-list-comma-newline-before`](https://stylelint.io/user-guide/rules/value-list-comma-newline-before/), [`value-list-max-empty-lines`](https://stylelint.io/user-guide/rules/value-list-max-empty-lines/)

### Shorthand property

Redundant property values must be written in shorthand notation.

```css
.selector {
  margin: 1em 1em 1em 1em;
}
```

Good

```css
.selector {
  margin: 1em;
}
```

Stylelint: [`shorthand-property-no-redundant-values`](https://stylelint.io/user-guide/rules/shorthand-property-no-redundant-values/)

### Property

Property must be written in lowercase.

Bad

```css
body {
  Margin: 0;
}
```

Good

```css
body {
  margin: 0;
}
```

Stylelint: [`property-case`](https://stylelint.io/user-guide/rules/property-case/)

---

Vender prefixes must not be used in property name. Use [Autoprefixer](https://github.com/postcss/autoprefixer) to add them depending on browser support.

Bad

```css
body {
  -webkit-transform: scale(1);
}
```

Good

```css
body {
  transform: scale(1);
}
```

Stylelint: [`property-no-vendor-prefix`](https://stylelint.io/user-guide/rules/property-no-vendor-prefix/)

### Keyframe declaration

Keyframe declaration must not have `!important`.

Bad

```css
@keyframes animation {

  100% {
    opacity: 1 !important;
  }

}
```

Good

```css
@keyframes animation {

  100% {
    opacity: 1;
  }

}
```

Stylelint: [`keyframe-declaration-no-important`](https://stylelint.io/user-guide/rules/keyframe-declaration-no-important/)

### Declaration

Declaration value must have single space before `!important` keyword.
It is recommended not using `!important` at all.

Bad

```css
.selector {
  color: #000! important;
}
```

Good

```css
.selector {
  color: #000 !important;
}
```

Best

```css
.selector {
  color: #000;
}
```

Stylelint: [`declaration-bang-space-after`](https://stylelint.io/user-guide/rules/declaration-bang-space-after/), [`declaration-bang-space-before`](https://stylelint.io/user-guide/rules/declaration-bang-space-before/), [`declaration-no-important`](https://stylelint.io/user-guide/rules/declaration-no-important/)

---

Declaration requires no space before colon and single space after them.

Bad

```css
.selector {
  color :#000;
}
```

Good

```css
.selector {
  color: #000;
}
```

Stylelint: [`declaration-colon-space-after`](https://stylelint.io/user-guide/rules/declaration-colon-space-after/), [`declaration-colon-space-before`](https://stylelint.io/user-guide/rules/declaration-colon-space-before/)

---

Declarations must not have empty lines between them.

Bad

```css
.selector {
  background-color: #fff;

  color :#000;
}
```

Good

```css
.selector {
  background-color: #fff;
  color: #000;
}
```

Stylelint: [`declaration-empty-line-before`](https://stylelint.io/user-guide/rules/declaration-empty-line-before/)

### Selector list

Each selector of a selector list must be on it's own line.

Bad

```css
html ,body {
  color: #000;
}
```

Good

```css
html,
body {
  color: #000;
}
```

Stylelint: [`selector-list-comma-newline-after`](https://stylelint.io/user-guide/rules/selector-list-comma-newline-after/), [`selector-list-comma-newline-before`](https://stylelint.io/user-guide/rules/selector-list-comma-newline-before/), [`selector-list-comma-space-after`](https://stylelint.io/user-guide/rules/selector-list-comma-space-after/), [`selector-list-comma-space-before`](https://stylelint.io/user-guide/rules/selector-list-comma-space-before/)

### Rule

Rules must be separated by empty line.

Bad

```css
a {
  …
}
b {
  …
}
```

Good

```css
a {
  …
}

b {
  …
}
```

Stylelint: [`rule-empty-line-before`](https://stylelint.io/user-guide/rules/rule-empty-line-before/)

### Media query list

Media query list must be single line with space required after comma.

Bad

```css
@media only print ,
       screen and (min-width: 48em) {
  …
}
```

Good

```css
@media only print, screen and (min-width: 48em) {
  …
}
```

Stylelint: [`media-query-list-comma-newline-after`](https://stylelint.io/user-guide/rules/media-query-list-comma-newline-after/), [`media-query-list-comma-newline-before`](https://stylelint.io/user-guide/rules/media-query-list-comma-newline-before/), [`media-query-list-comma-space-after`](https://stylelint.io/user-guide/rules/media-query-list-comma-space-after/), [`media-query-list-comma-space-before`](https://stylelint.io/user-guide/rules/media-query-list-comma-space-before/)

### Comment

Comments must always have a newline before them. There must always be whitespace inside comment markers.

Bad

```css
.selector { … }
/*Comment*/
```

Good

```css
.selector { … }

/* Comment */
```

Stylelint: [`comment-empty-line-before`](https://stylelint.io/user-guide/rules/comment-empty-line-before/), [`comment-whitespace-inside`](https://stylelint.io/user-guide/rules/comment-whitespace-inside/)
