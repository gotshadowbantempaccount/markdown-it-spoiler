# markdown-it-spoiler
[![npm version](https://badge.fury.io/js/%40traptitech%2Fmarkdown-it-spoiler.svg)](https://badge.fury.io/js/%40traptitech%2Fmarkdown-it-spoiler)
![check npm ci & run test](https://github.com/traPtitech/markdown-it-spoiler/workflows/check%20npm%20ci%20&%20run%20test/badge.svg)
![automatic publish](https://github.com/traPtitech/markdown-it-spoiler/workflows/automatic%20publish/badge.svg)
[![Dependabot Status](https://api.dependabot.com/badges/status?host=github&repo=traPtitech/markdown-it-spoiler)](https://dependabot.com)
> `!!spoiler!!` plugin for markdown-it markdown parser

`!!spoiler!!` => `<span class="spoiler">spoiler</span>`

## Installation
`$ npm i @traptitech/markdown-it-spoiler --save`

## Include
`var md = require('markdown-it')({
  multiline:  1,
  breaks: 		1, 
})
.use(require('@traptitech/markdown-it-spoiler'))`



## `frontPriorMode`(default: `false`)
### when `false`

`!!!spoiler!!` => `!<span class="spoiler">spoiler</span>`
`!!spoiler!!!` => `<span class="spoiler">spoiler!</span>`

### when `true`

`!!!spolier!!` => `<span class="spoiler">!spoiler</span>`
`!!spolier!!!` => `<span class="spoiler">spoiler</span>!`

### Styles

```
.spoiler:not(.show) {
	position: relative;
	font-size: 0;
	display: block;
}
.spoiler:not(.show) img {
	display: none
}
.spoiler.show {
	font-family: monospace, Monaco;
	white-space: normal;
	font-size: 14px;
	background-color: #f5f5f5;
}

.spoiler:not(.show)::after {
	background: #ecf0f1;
	content: "Show spoiler";
	padding: 1px 5px;
	color: #a19c9c;
	border-radius: 3px;
	cursor: pointer;
	width: 92px;
	height: 20px;
	display: block;
	font-size: 14px;
	white-space: nowrap;
}
```
## Jquery
```
$('body').on('click','span.spoiler', function(e) {
  $(this).addClass('show')
})
```

