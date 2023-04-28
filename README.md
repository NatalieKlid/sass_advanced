# sass_advanced

## Map data type in SCSS

```
// Map:
$colors: (
    primary: #000,
    secondary: #bdbdbd,
    tertiary: #dedede
)

// Usage:
h1 {
    color: map-get($colors, tertiary) // method map-get with parameters: name of the map, key to use from the map
}
```

## For loop

```
// HTML:
<p class="paragraph-1">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-2">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-3">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-4">Lorem ipsum dolor sit amet.</p>


// SCSS:
$colors: (
    1: #000,
    2: #bdbdbd,
    3: #dedede,
    4: green
)

@for $i from 1 through 4 {
    .paragraph-#{$i} { // #{$i} - interpolation
        color: map-get($colors, $i)
    }
}
```

## Each loop

```
// HTML:
<p class="paragraph-red">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-green">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-blue">Lorem ipsum dolor sit amet.</p>
<p class="paragraph-orange">Lorem ipsum dolor sit amet.</p>


// SCSS:
$colors: red green blue orange; // this is a "list" data type in scss

@each $color in $colors {
    .paragraph-#{$color} { 
        color: map-get($colors, $color)
    }
}
```

## If directive

```
@mixin headingSize($size) {
    @if($size == large) {
        font-size: 50px;
    } @else if($size == medium) {
        font-size: 40px;
    } @else {
        font-size: 20px;
    }
}

h1 {
    @include headingSize(medium); // result: font-size: 40px;
}
```