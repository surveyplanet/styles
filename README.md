# SurveyPlanet SCSS base styles

## Usage

```html
<style lang="scss">
	@use './node_modules/@surveyplanet/styles/index.scss' as *;
	body {
		color: $color--blue;
		font: $font--default;
	}
</style>
```
Note: using `as *` will disregard the namespace set by the filename so you don't need to specify the module followed by the variable name e.g.: `fonts.$font--default`.

### Alternate usage
You may only need a single module, you can import it like this:

```html
<style lang="scss">
	@use './node_modules/@surveyplanet/styles/src/colors.scss';
	.blue-txt {
		color: colors.$color--blue;
	}
</style>
```


## Colors

### Usage
```scss
@use src/colors as *
.button {
	background-color: $color--yellow;
}
```


### Blue

```scss
$color--blue
$color--blue-dark
```

### Gray

```scss
$color--white
$color--light
$color--dark
```

### Green

```scss
$color--green
$color--green-dark
```

### Pink

```scss
$color--pink
$color--pink-dark
```

### Purple

```scss
$color--purple-lightest
$color--purple-lighter
$color--purple-light
$color--purple
$color--purple-dark
```

### Yellow

```scss
$color--yellow
$color--yellow-dark
```

## Fonts


### Import Suisse Intl font
[Suisse Intl](https://www.swisstypefaces.com/fonts/suisse/) fonts family of fonts need to be loaded for these styles. The fonts are available in this package but need to be loaded like so:

```css
@use './fonts.scss';
load-suisse-font(); /* default: intl, regular*/
load-suisse-font(mono, bold);
```

...resulting in:
```css
@font-face {
	 font-family: "Suisse Intl";
	 src: url("src/fonts/suisse/intl/regular.woff2") format('woff2'),
	 url("src/fonts/suisse/intl/regular.woff") format('woff'), 
	 url("src/fonts/suisse/intl/regular.ttf") format('truetype');
}
@font-face {
	 font-family: "Suisse Mono Bold";
	 src: url("src/fonts/suisse/mono/bold.woff2") format('woff2'),
	 url("src/fonts/suisse/mono/bold.woff") format('woff'), 
	 url("src/fonts/suisse/mono/bold.ttf") format('truetype');
}
```

### Font Families
```scss
$font-family--serif
$font-family--default
```

### Font Sizes
```scss
$font--xsmall
$font--xsmall-bold
$font--small
$font--default
$font--medium
$font--default-bold
$font--medium-bold
$font--large
```

## Gutters

```scss
$gutter--quadruple
$gutter--triple
$gutter--double
$gutter
$gutter--half
$gutter--quarter
$gutter--eighth
$gutter--sixteenth
```

## Mixins

### Spin
The keyframes necessary to spin in a 360 degree circle.

#### Parameters
`$r`: total degrees to rotate. default: `360deg`

#### Example

```scss
@use "src/mixins" as *;
@include spin();
.button {
	animation: spin 1s linear infinite;
}
```

#### Result

```css
@keyframes spin {
	from {
		transform: rotate(0deg);
	}
	to {
		transform: rotate(360deg);
	}
}
.button {
	animation: spin 1s linear infinite;
}

```

### Pseudo
When using ::before and ::after you'll always need these three lines,

#### Parameters
`$display`: The display CSS property. default: `block`
`position`: The position CSS property. default: `absolute`
`content`: The element content. default: `''`

#### Example

```scss
@use "src/mixins" as *;
.button:after {
	@include pseudo()
}
```

#### Result

```css
.button:after {
    content: '';
    position: absolute;
    display: block;
}
```


### Triangle
Create a CSS generated triangle.

#### Parameters

`$color`: The color of the triangle. required
`$direction`: The triangle direction. Either `up`, `down`, `right`, `left`
`$size`: The size of the triangle. default: `6px`
`$position`: The position of the triangle. default: `absolute`
`$round`: Whether the triangle should be rounded or not. default: `false`

#### Example

```scss
@use "src/mixins" as *;
.popup:before {
	triangle(red, up)
}
```

#### Result

```css
.popup:before {
    content: '';
    position: absolute;
    display: block;
	border-left: 6px solid transparent;
	border-right: 6px solid transparent;
	border-bottom: 6px solid red;
	margin-bottom: 0 - round( 6px / 2.5 );
}

```


### Media query
Set media queries on a object.

#### Parameters

`$device`: One of: `phone`, `phone-wide`, `phablet`, `tablet-small`, `tablet`, `tablet-wide`, `desktop`, `desktop-wide`. required.
`$type`: min or max width default: min

#### Example

```scss
@use "src/mixins" as *;
.site-header {
    padding: 2rem;
    @include mq('tablet') {
        padding: 2rem;
    }
    @include mq('desktop') {
        padding: 4rem;
    }
}
```

#### Result

```css
.site-header {
    padding: 2rem;
    @media only screen and (min-width: 768px) {
        padding: 2rem;
    }
    @media only screen and (min-width: 1248px) {
        padding: 4rem;
    }
}

```


### Truncate

Truncate the text inside an element.

#### Parameters

`$width`: the max width of an element. required.

#### Example

```scss
@use "src/mixins" as *;
.title {
	truncate(100px);
}
```

#### Result

```css
.title {
    max-width: 100px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;

}
```



#### Fade
Fade in an element in or out

#### Parameters

`$direction`: A string indicating whether the element should fade `"in"` or `"out"`. default: `"out"`.

#### Example

```scss
@use "src/mixins" as *;
button {
	fade();
}
```

#### Result

```css
button {
    visibility: hidden;
    opacity: 0;
    transition: visibility 1s, opacity 1s;

}
```