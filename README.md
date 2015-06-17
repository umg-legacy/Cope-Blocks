# Cope-Blocks
A library of reusable code snippets that everyone can use to get stuff done on the COPE platform. Anyone can update this and request new things to be added using the issues tab (on the right ->). Just login/signup and raise a new bug.

To use, copy n paste into text editor (Sublime text, Text mate, Notepad. NOT WORD) and save in the format ```storename.css```
The go to the shop designs tab, click on the Custom style sheets tab. The file goes in the top 'stylesheet' input. Then save + refresh.

## The basics

To create a link that opens in a new tab/window. The ```target="_blank"``` does this for us. 
```html
<a href="//www.google.com/" target="_blank">Click here</a>
```

Instead of WRITING EVERYTHING IN CAPITALS you should use
```css 
.selector{ text-transform: uppercase; } 
```

## Cope 
To change the colors of headings on the help page(terms & conditions, delivery, privacy policy) 
```css
.reveal, .terms .col-mid a, .delivery .col-mid a, .privacy .col-mid a, .help .col-mid a, .terms .col-mid a:visited, .delivery .col-mid a:visited, .privacy .col-mid a:visited, .help .col-mid a:visited{ 
	color: #222; 
}
```

To make text centered on the categories pages
```css
.main .product{ text-align: center; }
```