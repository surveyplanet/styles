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
@use './node_modules/@surveyplanet/styles/index.scss' as *;
.button {
	background-color: $color--yellow;
	color: $color-dark;
}
```

| Property                  | Value   |
| ------------------------- | ------- |
| `$color--blue`            | #9ee4fa |
| `$color--blue-dark`       | #78c4ee |
| `$color--white`           | #ffffff |
| `$color--light`           | #f7f8f7 |
| `$color--dark`            | #262b35 |
| `$color--green`           | #a1fda5 |
| `$color--green-dark`      | #a1fda5 |
| `$color--pink`            | #ffb1e3 |
| `$color--pink-dark`       | #ea83c5 |
| `$color--purple-lightest` | #f6f1ff |
| `$color--purple-lighter`  | #ede2ff |
| `$color--purple-light`    | #baa5db |
| `$color--purple`          | #b598ff |
| `$color--purple-dark`     | #9a79ed |
| `$color--yellow`          | #ffe978 |
| `$color--yellow-dark`     | #fac766 |

## Fonts

### Import Suisse Intl font

[Suisse Intl](https://www.swisstypefaces.com/fonts/suisse/) fonts family of fonts need to be loaded for these styles. The fonts are available in this package but need to be loaded like so:

```css
@use './node_modules/@surveyplanet/styles/index.scss' as *;

load-suisse-font(); /* default: intl, regular*/
load-suisse-font(mono, bold);
```

...resulting in:

```css
@font-face {
	font-family: 'Suisse Intl';
	src: url('src/fonts/suisse/intl/regular.woff2') format('woff2'), url('src/fonts/suisse/intl/regular.woff')
			format('woff'), url('src/fonts/suisse/intl/regular.ttf') format('truetype');
}
@font-face {
	font-family: 'Suisse Mono Bold';
	src: url('src/fonts/suisse/mono/bold.woff2') format('woff2'), url('src/fonts/suisse/mono/bold.woff')
			format('woff'), url('src/fonts/suisse/mono/bold.ttf') format('truetype');
}
```

### Font families

| Property                | Value                                                         |
| ----------------------- | ------------------------------------------------------------- |
| `$font-family--serif`   | 'Suisse Works', 'Times New Roman', Times, serif               |
| `$font-family--sans`    | 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif |
| `$font-family--default` | $font-family--sans                                            |
| `$font-family--mono`    | 'Suisse Mono', 'Courier New', Courier, monospace              |

### Font sizes

| Property               | rem                   | px   |
| ---------------------- | --------------------- | ---- |
| `$font-size-10`        | 0.625rem              | 10px |
| `$font-size-12`        | 0.75rem               | 12px |
| `$font-size-14` (base) | 0.875rem              | 14px |
| `$font-size-default`   | $font-size-14 (alias) | 14px |
| `$font-size-16`        | 0.625rem              | 16px |
| `$font-size-18`        | 1.125rem              | 18px |
| `$font-size-20`        | 1.25rem               | 20px |
| `$font-size-24`        | 1.5rem                | 24px |
| `$font-size-28`        | 1.75rem               | 28px |
| `$font-size-32`        | 2rem                  | 32px |
| `$font-size-36`        | 2.25rem               | 36px |

### Fonts settings

| Property              | Value                                                       |
| --------------------- | ----------------------------------------------------------- |
| `$font--xsmall`       | normal normal $font-size-10/130% $font-family--default      |
| `$font--xsmall-bold`  | normal bold $font-size-10/130% $font-family--default        |
| `$font--small`        | normal normal $font-size-12/130% $font-family--default      |
| `$font--default`      | normal normal $font-size-default/140% $font-family--default |
| `$font--medium`       | $font--default // alias                                     |
| `$font--default-bold` | normal bold $font-size-default/140% $font-family--default   |
| `$font--medium-bold`  | $font--default-bold // alias                                |
| `$font--large`        | normal normal $font-size-16/140% $font-family--default      |

## Gutters

| Property             | rem      | px    |
| -------------------- | -------- | ----- |
| `$gutter--quadruple` | 25.6rem  | 256px |
| `$gutter--triple`    | 8rem     | 128px |
| `$gutter--double`    | 4rem     | 64px  |
| `$gutter`            | 2rem     | 32px  |
| `$gutter--half`      | 1rem     | 16px  |
| `$gutter--quarter`   | 0.5rem   | 8px   |
| `$gutter--eighth`    | 0.25rem  | 4px   |
| `$gutter--sixteenth` | 0.125rem | 2px   |

## Mixins

### Spin

The keyframes necessary to spin in a 360 degree circle.

#### Parameters

| Property    | Type  | Description              |
| ----------- | ----- | ------------------------ |
| `$r=360deg` | Sting | total degrees to rotate. |

#### Example

```scss
@use 'src/mixins' as *;
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

| Property            | Type   | Description                |
| ------------------- | ------ | -------------------------- |
| `$display=block`    | String | The display CSS property.  |
| `position=absolute` | String | The position CSS property. |
| `content=''`        | String | The element content.       |

#### Example

```scss
@use 'src/mixins' as *;
.button:after {
	@include pseudo();
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

| Property             | Type    | Description                                                             |
| -------------------- | ------- | ----------------------------------------------------------------------- |
| `$color`             | String  | The color of the triangle. (required)                                   |
| `$direction`         | String  | The triangle direction (required). Either `up`, `down`, `right`, `left` |
| `$size=6px`          | String  | The size of the triangle.                                               |
| `$position=absolute` | String  | The position of the triangle.                                           |
| `$round=false`       | Boolean | Whether the triangle should be rounded or not.                          |

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
	margin-bottom: 0 - round(6px / 2.5);
}
```

### Media query

Set media queries on a object.

#### Parameters

| Property    | Type   | Description                                                                                                                                  |
| ----------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `$device`   | String | The type of device (required). Either: `phone`, `phone-wide`, `phablet`, `tablet-small`, `tablet`, `tablet-wide`, `desktop`, `desktop-wide`. |
| `$type=min` | String | `min` or `max` width                                                                                                                         |

#### Example

```scss
@use 'src/mixins' as *;
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

| Property | Type   | Description                             |
| -------- | ------ | --------------------------------------- |
| `$width` | Number | The max width of an element (required). |

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

| Property         | Type   | Description                                        |
| ---------------- | ------ | -------------------------------------------------- |
| `$direction=out` | String | Whether the element should fade `"in"` or `"out"`. |

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
