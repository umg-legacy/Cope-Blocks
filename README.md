# Cope-Blocks
A library of reusable code snippets that everyone can use to get stuff done on the COPE platform. Anyone can update this and request new things to be added using the issues tab (on the right ->). Just login/signup and raise a new bug.

To use, copy n paste into text editor ([Sublime text](//www.sublimetext.com/), [Atom](//atom.io/), Text mate, Notepad. **NOT WORD**) and save as a .css (Cascading Style Sheet) file in the format ```storename.css```
The go to the shop designs tab, click on the Custom style sheets tab. The file goes in the top 'stylesheet' input. Then save + refresh.

## The basics

### Open Links in new windows
To create a link that opens in a new tab/window. The ```target="_blank"``` does this for us. 
```html
<a href="//www.google.com/" target="_blank">Click here</a>
```

### Uppercase Text
Instead of WRITING EVERYTHING IN CAPITALS you should use
```css 
.selector{ text-transform: uppercase; } 
```
or inline
```html
<p style="text-transform: uppercase;">Some text that you want in capitals</p>
```

### Bold text
Using the ```html <b> ``` tag is oldschool and no longer semantically correct. Its better to use 
```html
<p class="preorder-text">Enter some <span>Bold</span> text here</p>
```
using css to style the span
```css
.preorder-text span{ font-weight: bold; }
```
or inline
```html
<p>Enter some <span style="font-weight: bold;">Bold</span> text here</p>
```
### Centered text
To make text center aligned (you can do left and right aligned with the same method)
```html
<p class="preorder-text">Enter some text here</p>
```
using css to style the span
```css
.preorder-text{ text-align: center; }
```
or inline
```html
<p style="text-align: center;">Enter some text here</p>
```
If you run into issues try adding this
```css
display: block;
width: 100%;
```
### Lists
Don't make lists with p tags or individually number list items. There is an easier way.

#### Unordered lists
For lists without numbers
```html
<ul>
	<li>List Item</li>
	<li>List Item</li>
	<li>List Item</li>
</ul>
```
Gives you a list that looks like
- List Item
- List Item
- List Item

#### Ordered lists
For lists with numbers
```html
<ol>
	<li>List Item</li>
	<li>List Item</li>
	<li>List Item</li>
</ol>
```
Gives you a list that looks like

1. List Item
2. List Item
3. List Item

You can get rid of bullet points or bumbers by using ```text-decoration: none;```


## Cope 

### Help Pages
To change the colors of headings on the help page(terms & conditions, delivery, privacy policy) 
```css
.reveal, .terms .col-mid a, .delivery .col-mid a, .privacy .col-mid a, .help .col-mid a, .terms .col-mid a:visited, .delivery .col-mid a:visited, .privacy .col-mid a:visited, .help .col-mid a:visited{ 
	color: #222; 
}
```
### Categories Pages
To make product info text centered on the categories pages
```css
.main .product{ text-align: center; }
```

### Basket Dropdown
The dropdown basket can be styled too.

To make the title like the same color as the rest of the minicart text:
```css
.mini-cart .title a{
	color: inherit;
}
```
To change to colour of the "view basket" link:
```css
.mini-footer > a {
  color: red;
}
```
### Product Pages
To remove Digital tables
```css
.digital{display: none;}
```

To get rid of table styling
```css
.product .table, .product table tr:nth-child(even), .product table th, .product table td{
	background: none;
	border: 0;
}
```


### Checkout
Checkout styling must be in a new ```storename-checkout.css``` file and is uploaded to the checkout input block.

Buttons can be styled (color defines the text colour)
```css
.next, button{
	color: #ff0000;
	background-color: #fff;
}
.next:hover, .next:active, .next:focus, button:hover,  .button:active, .button:focus{
	color: #fff;
	background-color: #ff0000;
}
```

The forgotten password link can be changed (```text decoration: none``` removes link underline)
```css
a{
	color: #ff0000;
	text-decoration: none;
}
```