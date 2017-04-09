[![Build Status](https://travis-ci.org/marcobiedermann/css-style-guide.svg?branch=master)](https://travis-ci.org/marcobiedermann/css-style-guide)
[![devDependency Status](https://david-dm.org/marcobiedermann/css-style-guide/dev-status.svg)](https://david-dm.org/marcobiedermann/css-style-guide#info=devDependencies)

# CSS Style Guide

A styleguide which helps you write better, performant, structured, scalable and maintainable CSS.

## Table of contents

* [CSS](#css)
	* [Color](#color)
	* [Font](#font)
	* [Number](#number)
	* [String](#string)
	* [Length](#length)

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

Number must never have a leading zero.

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
