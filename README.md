# Cope-Blocks
A library of reusable code snippets that everyone can use to get stuff done on the COPE platform. Any can update this and request new things to be added using pull requests

## The basics

To create a link that opens in a new tab/window. The ```target="_blank"``` does this for us. 
```html
<a href="//www.google.com/" target="_blank">Click here</a>
```

## Cope 
To change the colors of help(terms & conditions, delivery, privacy policy) page headings
```css
.reveal, .terms .col-mid a, .delivery .col-mid a, .privacy .col-mid a, .help .col-mid a, .terms .col-mid a:visited, .delivery .col-mid a:visited, .privacy .col-mid a:visited, .help .col-mid a:visited{ 
	color: #222; 
}
```