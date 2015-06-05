# Heres a place to put all of those reusable bits of code for store builds

**Warning**: Contains precompiled code. Not suitable for cope upload (or vegetarians)

## New Grid
This can replace the current grid which uses explicit identifiers.
@args: $numberofproducts - (int) the number of products in a row
			 $gutters - (int) Percentage gutters (no % sign)
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
