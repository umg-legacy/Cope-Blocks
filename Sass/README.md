# Reusable bits of code for store builds

**Warning**: Contains precompiled code. Not suitable for cope upload (or vegetarians)

## New Grid
This can replace the current grid which uses explicit identifiers.
args: 
⋅⋅⋅$numberofproducts - (int) the number of products in a row
⋅⋅⋅$gutters - (int) Percentage gutters (no % sign)
```sass
@mixin new-grid($numberofproducts, $gutters) {
  $margin: 0;
  @if $numberofproducts > 1 {
    $margin: ($numberofproducts - 1) * $gutters;
  } @else {
    $margin: 0;
  }
  .product, .product:nth-child(n){
    display: inline-block;
    vertical-align: top;
    width: (100% - $margin) / $numberofproducts;
    margin: 0 -4px 3em #{$gutters + '%'};
  }
  .product:nth-child(#{$numberofproducts}n + 1){
    margin-left: 0;
  }
}
```
To use
```sass
@include new-grid(4, 1.5);
```

##Flexbox
Flexbox offers some amazing layout options. Lets start using it as part of progressive enhancement (not available in ie8 + 9)

###Mixins
Use the flexbox mixin on containers to init flexbox. This contains the work arounds for older browsers
```sass
@mixin flexbox() {
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
}
```

The flex mixin is for use on individual blocks. It is the shorthand for flex-grow, flex-shrink and flex-basis combined
```sass
@mixin flex($values) {
  -webkit-box-flex: $values;
  -moz-box-flex:  $values;
  -webkit-flex:  $values;
  -ms-flex:  $values;
  flex:  $values;
}
```

Order is a mixin used for changing the order of elements within the flexbox container
```sass
@mixin order($val) {
  -webkit-box-ordinal-group: $val;  
  -moz-box-ordinal-group: $val;     
  -ms-flex-order: $val;     
  -webkit-order: $val;  
  order: $val;
}
```

We can improve the grid by using flexbox. I have put flexbox inside a media query in order to keep the default mobile styling (where the product image is inline with product information).

Initially there are 2 products per row expanding to 3 at 768px. I've used % values so the images grow to fit the block. At the point where the window is bigger than the number of products per row (3) + their margin the product blocks are static and the number of products per row increases for bigger screens.
```sass 
$flex-product-width: 17.815em; //275px
$flex-product-margin: 3.5em; //Aprox total margin for 3 products based on 1%;

//481px - flexbox not on for super small screens
@media (min-width: ($aside-width + 0.5em + 30.0625em)){ 
  .flexbox { //On body class
    .col-mid{
      max-width: 100%;
    }
    .prod-feat, #category-page {
      @include flexbox();
      -webkit-flex-flow: row wrap;
      flex-flow: row wrap;
      align-items: flex-start;
      align-content: flex-start;
    }

    .main .product, .main .product > a{
      @include flexbox;
      -webkit-flex-flow: row wrap;
      flex-flow: row wrap;
      -webkit-justify-content: center;
      justify-content: center;
      width: 49%; //If you want them to scale
      max-width: $img-width; // when this is reached the it stops scaling and number of items per row increases
      margin: 0 0.5% 2em;
      dt, dd{ width: 100%; }
      .price, .was{ 
        width: 25%; 
        margin: 0;
      }
    }
    .main .product > a{ width: 100%; margin: 0;}
    .product .col-mid{ max-width: $content-width}
  } 
}

@media (min-width: (48em){ //768px
  .flexbox{
    .main .product{
      width: 32%;
    }
    // .prod-feat {
    //   -webkit-justify-content: center;
    //   justify-content: center;
    // }
    #category-page{
      -webkit-justify-content: flex-start;
      justify-content: flex-start;
    }
  }
}
//The point where flexbox nolonger devides the total width by number of products to make the expand to full width. After this it makes the no. of products in a row bigger
//(Products width x number of products per row) + product margin = ~1162px
@media (min-width: (($flex-product-width * 3) + $flex-product-margin))){
  .flexbox{
    .main .product{
      width: $flex-product-width; //if you want them to redraw
    }
  }
}
```