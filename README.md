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

You can get rid of bullet points or numbers by using ```text-decoration: none;```

You can group idential css rules by using commas
```css
.oneSelector,
.twoSelector,
.threeSelector{
	display:none;
}
```

### Media Queries
Media queries allow you to apply styling at a breakpoint (For example: screensize). An example of this is to hide the mobile dropdown menu on devices bigger than 768px.
```css
@media(min-width:768px){
	//Put styles here
}
```
Breakpoints reflect where the content 'breaks'(defined as looking sub-optimal).
 
Common breakpoints are:
```css
/* Mobile styles are outside of media queries */

@media(min-width:480px){
	/* Put Large mobile styles here */
}
@media(min-width:768px){
	/* Put Tablet styles here */
}
@media(min-width:991px){
	/* Put small desktop styles here */
}
@media(min-width:1200px){
	/* Put large desktop styles here */
}

```

You can read more about breakpoints on the [Google developer portal](https://developers.google.com/web/fundamentals/layouts/rwd-fundamentals/how-to-choose-breakpoints)

## Cope 

###Image sizes

- Logo Images (jpg, png, gif) Max-width: 1200px
- Secure Logo (png, gif) - Aprox 300px x 105px
- Mail Logo (jpg, png, gif) - 266px x 120px
- Invoice Logo (png, gif) - 300px x 200px
- Shortcut Icon / Favicon (ico). - 16px 16px
- Apple touch logo (png) - 180px x 180px

###Product List Selectors
Trim down product list information (delete as appropriate)
```css
.main .product .image, /* Selects Image */
.main .product .title,  /* Selects title */
.main .product .format, /* Selects format */
.main .product .dispatch, /* Selects dispatch */
.main .product .price, /* Selects price */
.main .product .was{ /* Selects was price */
	display:none;
}
```

### Background attachment
To override the template styling that makes the background scroll on mobile use:
```css
@media (max-width: 48em){
	body {
	  background-attachment: fixed;
	}
}
```

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

~~To make the title like the same color as the rest of the minicart text:~~
~~.mini-cart .title a{ color: inherit; }~~

Best Practice is to turn of basket links in the cope shop settings window

To change to colour of the "view basket" link:
```css
.mini-footer > a, .mini-footer > a:visited {
  color: red;
}
```
To change to colour of the Add/remove buttons:
```css
.add, .remove {
  background-color: purple;
  color: white;
}
```

### Product Pages
To hide 'Buy now - back in stock soon'
```css
.prod-details .dispatch{
	display: none;
}
```
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
To get rid of Running time row on digital products
```css
.product .digital tbody:last-of-type{
    display: none;
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

### Removing Social Media Bubbles

To remove the social media bubbles on product pages.

```css

.js .social-buttons {
  height: 23px !important;
  width: auto;
  overflow: hidden;
}

iframe#twitter-widget-0{   
    top: 0px!important;
    }
}

span.pinterest-pinit a { display: none!important; }

.googleplus-one div{
    height: 22px!important;
    overflow: hidden;
  }
  iframe {
    position: relative!important;
    top: -39px!important;
  }
}

.facebook-like span{
    height: 22px;
    overflow: hidden;
  }
}
```


### Removing Social Media Icons / Bubbles

To remove social media completely.

```css

.social-buttons {
display:none;
}
```

To remove social media completely.

```css

.social-buttons {
display:none;
}
```

### Sound of Vinyl - 25% off Page

How to update  [Sound of Vinyl](//thesoundofvinyl.com/*/Records-Of-The-Week/)

#### - Shorten the product descriptions.
Work out where you want the wording to end - add the div class around the text you want to HIDE.




```html

<div class="more-info">
Tracklist: 
</div>

```

#### - Update the Products
They are set up as Frontend Segments. 

```css

ROW-product1
ROW-product2
ROW-product3

```

Edit Product Frontend Segment > Display Product > CHOOSE YOU PRODUCT

DONE! they should be updated on the Record of the week page! 