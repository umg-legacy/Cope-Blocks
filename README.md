# Cope-Blocks
A library of reusable code snippets for the COPE shops. If you need something that is not in here, please email GlobalD2C.newstore@umusic.com


## CSS snippets

To use, copy n paste into your text editor ([Sublime text](https://www.sublimetext.com/), [Visual Studio Code](https://code.visualstudio.com/), Notepad. **Not Word**) and save as a .css (Cascading Style Sheet) file in the format ```storename.css```
The go to the shop designs tab, click on the Custom style sheets tab. The file goes in the top 'stylesheet' input. Then save + refresh.

### Tracklist tables - Remove the striped background and borders
```css
/* Tracklistings */
.physicalalbumtracks {
  margin: 2em 0;
}
.physicalalbumtracks thead {
  border: 0;
}
.physicalalbumtracks thead tr {
  display: none;
}
.physicalalbumtracks thead tr:last-child {
  display: table-row;
}
.col-mid .physicalalbumtracks tr {
  background: none;
  border: 0;
}
.physicalalbumtracks th {
  padding-left: 0;
  font-weight: bold;
}
```
### Hide Digital tracks
```css
.digital { display: none; }
```

### Help page headings

Change the colors of headings on the help page (terms & conditions, delivery, privacy policy)
```css
.reveal, .terms .col-mid a, .delivery .col-mid a, .privacy .col-mid a, .help .col-mid a, .terms .col-mid a:visited, .delivery .col-mid a:visited, .privacy .col-mid a:visited, .help .col-mid a:visited{
	color: #222;
}
```

## HTML snippets

To be used in HTML snippets or in descriptions

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




## Other Cope settings

### Image sizes

- Logo Images (jpg, png, gif) Max-width: 1200px
- Secure Logo (png, gif) - Aprox 300px x 105px
- Mail Logo (jpg, png, gif) - 266px x 120px
- Invoice Logo (png, gif) - 300px x 200px
- Shortcut Icon / Favicon (ico). - 16px 16px
- Apple touch logo (png) - 180px x 180px
