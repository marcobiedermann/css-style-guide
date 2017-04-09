[![Build Status](https://travis-ci.org/marcobiedermann/css-style-guide.svg?branch=master)](https://travis-ci.org/marcobiedermann/css-style-guide)
[![devDependency Status](https://david-dm.org/marcobiedermann/css-style-guide/dev-status.svg)](https://david-dm.org/marcobiedermann/css-style-guide#info=devDependencies)

# CSS Style Guide

A styleguide which helps you write better, performant, structured, scalable and maintainable CSS.

## Table of contents

* [CSS](#css)
	* [Color](#color)

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
