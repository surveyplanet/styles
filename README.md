# SurveyPlanet SCSS base styles

## Usage

```html
<style lang="scss">
	@use '@surveyplanet/styles' as *;
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
	@use '@surveyplanet/styles/src/colors.scss';
	.blue-txt {
		color: colors.$color--blue;
	}
</style>
```

## Colors pallets

### Slate - gray

| Property              | Value     |
| --------------------- | --------- |
| `$color--slate-light` | `#dcdee1` |
| `$color--slate`       | `#737a87` |
| `$color--slate-dark`  | `#262b35` |

### Magnolia - light purple

| Property                     | Value     |
| ---------------------------- | --------- |
| `$color--light-purple-light` | `#f4f0ff` |
| `$color--light-purple`       | `#ece5ff` |
| `$color--light-purple-dark`  | `#baa5db` |

### Lavender - purple

| Property               | Value     |
| ---------------------- | --------- |
| `$color--purple-light` | `#dbccff` |
| `$color--purple`       | `#b598ff` |
| `$color--purple-dark`  | `#9a79ed` |

### Sky - blue

| Property             | Value     |
| -------------------- | --------- |
| `$color--blue-light` | `#d8f4fd` |
| `$color--blue`       | `#9ee4fa` |
| `$color--blue-dark`  | `#78c4ee` |

### Spring - green

| Property              | Value     |
| --------------------- | --------- |
| `$color--green-light` | `#d9fedb` |
| `$color--green`       | `#a1fda5` |
| `$color--green-dark`  | `#7be492` |

### Bubble Gum - pink

| Property             | Value     |
| -------------------- | --------- |
| `$color--pink-light` | `#ffd8f1` |
| `$color--pink`       | `#ffb1e3` |
| `$color--pink-dark`  | `#ea83c5` |

### Sunrise - yellow

| Property               | Value     |
| ---------------------- | --------- |
| `$color--yellow-light` | `#fff5bc` |
| `$color--yellow`       | `#ffe978` |
| `$color--yellow-dark`  | `#fac766` |

### Shades

| Property                | Value                |
| ----------------------- | -------------------- |
| `$color--white`         | `#ffffff`            |
| `$color--black` (alias) | `$color--slate-dark` |

### Usage

```scss
@use '@surveyplanet/styles' as *;
.button {
	background-color: $color--yellow;
	color: $color-slate-dark;
}
```

## Fonts

### Import Suisse Intl font

[Suisse Intl](https://www.swisstypefaces.com/fonts/suisse/) fonts family of fonts need to be loaded for these styles.

#### Fonts available

| Family | Style          | Usage                                      |
| ------ | -------------- | ------------------------------------------ |
| cond   | bold           | `load-suisse-font(cond, bold)`             |
| cond   | thin           | `load-suisse-font(cond, thin)`             |
| intl   | black          | `load-suisse-font(intl, black)`            |
| intl   | blackitalic    | `load-suisse-font(intl, blackitalic)`      |
| intl   | bold           | `load-suisse-font(intl, bold)`             |
| intl   | bolditalic     | `load-suisse-font(intl, bolditalic)`       |
| intl   | book           | `load-suisse-font(intl, book)`             |
| intl   | bookitalic     | `load-suisse-font(intl, bookitalic)`       |
| intl   | light          | `load-suisse-font(intl, light)`            |
| intl   | lightitalic    | `load-suisse-font(intl, lightitalic)`      |
| intl   | medium         | `load-suisse-font(intl, medium)`           |
| intl   | mediumitalic   | `load-suisse-font(intl, mediumitalic)`     |
| intl   | regular        | `load-suisse-font(intl, regular)`          |
| intl   | semibold       | `load-suisse-font(intl, semibold)`         |
| intl   | thinitalic     | `load-suisse-font(intl, thinitalic)`       |
| intl   | ultralight     | `load-suisse-font(intl, ultralight)`       |
| mono   | bold           | `load-suisse-font(mono, bold)`             |
| mono   | regular        | `load-suisse-font(mono, regular)`          |
| mono   | thin           | `load-suisse-font(mono, thin)`             |
| neue   | light          | `load-suisse-font(neue, light)`            |
| neue   | lightitalic    | `load-suisse-font(neue, lightitalic)`      |
| neue   | medium         | `load-suisse-font(neue, medium)`           |
| neue   | mediumitalic   | `load-suisse-font(neue, mediumitalic)`     |
| neue   | regular        | `load-suisse-font(neue, regular)`          |
| neue   | thin           | `load-suisse-font(neue, thin)`             |
| screen | bold           | `load-suisse-font(screen, bold)`           |
| screen | bolditalic     | `load-suisse-font(screen, bolditalic)`     |
| screen | light          | `load-suisse-font(screen, light)`          |
| screen | lightitalic    | `load-suisse-font(screen, lightitalic)`    |
| screen | medium         | `load-suisse-font(screen, medium)`         |
| screen | mediumitalic   | `load-suisse-font(screen, mediumitalic)`   |
| screen | monitor        | `load-suisse-font(screen, monitor)`        |
| screen | monitoritalic  | `load-suisse-font(screen, monitoritalic)`  |
| screen | regular        | `load-suisse-font(screen, regular)`        |
| screen | regularitalic  | `load-suisse-font(screen, regularitalic)`  |
| screen | semibold       | `load-suisse-font(screen, semibold)`       |
| screen | semibolditalic | `load-suisse-font(screen, semibolditalic)` |
| screen | thin           | `load-suisse-font(screen, thin)`           |
| screen | thinitalic     | `load-suisse-font(screen, thinitalic)`     |
| works  | bold           | `load-suisse-font(works, bold)`            |
| works  | bolditalic     | `load-suisse-font(works, bolditalic)`      |
| works  | book           | `load-suisse-font(works, book)`            |
| works  | bookitalic     | `load-suisse-font(works, bookitalic)`      |
| works  | medium         | `load-suisse-font(works, medium)`          |
| works  | regular        | `load-suisse-font(works, regular)`         |

#### Load fonts with mixin

Suisse fonts are not available by default and need to be loaded using the mixins provided

```css
@use '@surveyplanet/styles/mixins.scss' as *;

load-suisse-font(); /* default: intl, medium*/
load-suisse-font(mono, bold);
```

##### Result

```css
@font-face {
	font-family: 'Suisse Intl';
	src: url('src/fonts/suisse/intl/medium.woff2') format('woff2'), url('src/fonts/suisse/intl/medium.woff')
			format('woff'), url('src/fonts/suisse/intl/medium.ttf') format('truetype');
}
@font-face {
	font-family: 'Suisse Mono Bold';
	src: url('src/fonts/suisse/mono/bold.woff2') format('woff2'), url('src/fonts/suisse/mono/bold.woff')
			format('woff'), url('src/fonts/suisse/mono/bold.ttf') format('truetype');
}
```

### Font families

| Property                | Value                                                                |
| ----------------------- | -------------------------------------------------------------------- |
| `$font-family--serif`   | 'Suisse Works', 'Times New Roman', Times, serif                      |
| `$font-family--sans`    | 'Suisse Intl Medium', 'Helvetica Neue', Helvetica, Arial, sans-serif |
| `$font-family--default` | $font-family--sans                                                   |
| `$font-family--mono`    | 'Suisse Mono', 'Courier New', Courier, monospace                     |

### Font sizes

| Property                      | rem            | px   |
| ----------------------------- | -------------- | ---- |
| `$font-size--10`              | 0.625rem       | 10px |
| `$font-size--12`              | 0.75rem        | 12px |
| `$font-size--14` (base)       | 0.875rem       | 14px |
| `$font-size--default` (alias) | $font-size--14 | 14px |
| `$font-size--16`              | 1rem           | 16px |
| `$font-size--18`              | 1.125rem       | 18px |
| `$font-size--20`              | 1.25rem        | 20px |
| `$font-size--24`              | 1.5rem         | 24px |
| `$font-size--28`              | 1.75rem        | 28px |
| `$font-size--32`              | 2rem           | 32px |
| `$font-size--36`              | 2.25rem        | 36px |

### Font weights

| Property                    | Weight | Description         |
| --------------------------- | ------ | ------------------- |
| `$font-weight--thin`        | 100    | Thin                |
| `$font-weight--extra-light` | 200    | Extra (ultra) light |
| `$font-weight--light`       | 300    | Light               |
| `$font-weight--normal`      | 400    | Normal              |
| `$font-weight--medium`      | 500    | Medium              |
| `$font-weight--semi-bold`   | 600    | Semi (demi) bold    |
| `$font-weight--bold`        | 700    | Bold                |
| `$font-weight--extra-bold`  | 800    | Extra (ultra) bold  |
| `$font-weight--black`       | 900    | Black (heavy)       |

### Fonts shorthand

| Property                      | Value                                                                                        |
| ----------------------------- | -------------------------------------------------------------------------------------------- |
| `$font--xsmall`               | normal normal 0.625rem/130% 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif    |
| `$font--xsmall-bold`          | normal bold 0.625rem/130% 'Suisse Intl', 'Helvetica Neue Bold', Helvetica, Arial, sans-serif |
| `$font--small`                | normal normal 0.75rem/130% 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif     |
| `$font--default`              | normal normal 0.875rem/140% 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif    |
| `$font--medium` (alias)       | $font--default                                                                               |
| `$font--default-bold`         | normal bold 0.875rem/140% 'Suisse Intl', 'Helvetica Neue Bold', Helvetica, Arial, sans-serif |
| `$font--medium-bold` ( alias) | $font--default-bold                                                                          |
| `$font--large`                | normal normal 1rem/140% 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif        |

#### Usage

```scss
body {
	font: $font--default;
}
```

Computed result:

```css
body {
	font-style: normal;
	font-weight: normal;
	font-size: 0.875rem;
	line-height: 140%;
	font-family: 'Suisse Intl', 'Helvetica Neue', Helvetica, Arial, sans-serif;
}
```

## Sizes

### Base sizes

| Property     | rem       | px    |
| ------------ | --------- | ----- |
| `$size--1`   | 0.0625rem | 1px   |
| `$size--2`   | 0.125rem  | 2px   |
| `$size--4`   | 0.25rem   | 4px   |
| `$size--6`   | 0.375rem  | 6px   |
| `$size--8`   | 0.5rem    | 8px   |
| `$size--9`   | 0.5625rem | 9px   |
| `$size--10`  | 0.625rem  | 10px  |
| `$size--11`  | 0.6875rem | 11px  |
| `$size--12`  | 0.75rem   | 12px  |
| `$size--14`  | 0.875rem  | 14px  |
| `$size--16`  | 1rem      | 16px  |
| `$size--18`  | 1.125rem  | 18px  |
| `$size--20`  | 1.25rem   | 20px  |
| `$size--24`  | 1.5rem    | 24px  |
| `$size--28`  | 1.75rem   | 28px  |
| `$size--32`  | 2rem      | 32px  |
| `$size--36`  | 2.25rem   | 36px  |
| `$size--40`  | 2.5rem    | 40px  |
| `$size--44`  | 2.75rem   | 44px  |
| `$size--48`  | 3rem      | 48px  |
| `$size--52`  | 3.25rem   | 52px  |
| `$size--56`  | 3.5rem    | 56px  |
| `$size--60`  | 3.75rem   | 60px  |
| `$size--64`  | 4rem      | 64px  |
| `$size--72`  | 4.5rem    | 72px  |
| `$size--80`  | 5rem      | 80px  |
| `$size--96`  | 6rem      | 96px  |
| `$size--128` | 8rem      | 128px |
| `$size--256` | 16rem     | 256px |

### Gutters

| Property                  | rem      | px    |
| ------------------------- | -------- | ----- |
| `$size-gutter--quadruple` | 25.6rem  | 256px |
| `$size-gutter--triple`    | 8rem     | 128px |
| `$size-gutter--double`    | 4rem     | 64px  |
| `$size-gutter`            | 2rem     | 32px  |
| `$size-gutter--half`      | 1rem     | 16px  |
| `$size-gutter--quarter`   | 0.5rem   | 8px   |
| `$size-gutter--eighth`    | 0.25rem  | 4px   |
| `$size-gutter--sixteenth` | 0.125rem | 2px   |

### Radius sizes

| Property                | px   |
| ----------------------- | ---- |
| `$size-radius--small`   | 3px  |
| `$size-radius--default` | 5px  |
| `$size-radius--large`   | 10px |

### Size utilities

| Property               | Value       | description                                                                                                                                                                                                                                                                            |
| ---------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `$size--full`          | 100%        | Set the element size to 100%                                                                                                                                                                                                                                                           |
| `$size--screen-width`  | 100vw       | Set the element size to 100% of the viewport width                                                                                                                                                                                                                                     |
| `$size--screen-height` | 100vh       | Set the element size to 100% of the viewport hight                                                                                                                                                                                                                                     |
| `$size--min`           | min-content | The [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-content) sizing keyword represents the intrinsic minimum width of the content. For text content this means that the content will take all soft-wrapping opportunities, becoming as small as the longest word. |
| `$size--max`           | max-content | The [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content) sizing keyword represents the intrinsic maximum width or height of the content. For text content this means that the content will not wrap at all even if it causes overflows.                       |
| `$size--fit`           | fit-content | [`fit-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content) sets the width of an element to use all available space.                                                                                                                                                 |

## Mixins

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

## Animation

Animation are just mixins that produce keyframes that can be used in animations

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

### Fade in out

Fade an element in then fade it out.

#### Parameters

| Property | Type   | Description                      |
| -------- | ------ | -------------------------------- |
| `$min=0` | Number | The minimum opacity of the fade. |
| `$min=1` | Number | The maximum opacity of the fade. |

#### Example

```scss
@use 'src/mixins' as *;
@include fadeInOut();
.pulse {
	animation: fadeinout 1s linear infinite;
}
```

#### Result

```css
@keyframes fadeinout {
	0%,
	100% {
		opacity: 0;
	}
	50% {
		opacity: 1;
	}
}
.pulse {
	animation: fadeinout 1s linear infinite;
}
```
