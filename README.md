# Sass (scss) Tutorial
___

#### We link the regular CSS style sheet file (.css) in the HTML file, and we make and name an SCSS (.scss) style sheet file. Live Sass compiler extention of VS Code compiled .scss file into regular .css after clicking on "watch Sass" button on the bar at the bottom.

#### Live sass compiler extension created 2 css file. css.map file we don't need to worry about, but in regular .css style file we shouldn't make any changes because those will be overwritten with any saved changes in Sass (scss) file.

## Sass variables, Sass maps, Nesting in Sass, Sass funtions, Sass Mixins, Math in Sass, Detecting BG clr to set TEXT clr, Sass Each loops

### Variables
##### syntax for making and using Sass variables
<pre><code>
$myColor: #4662ff;

body {
    background-color: $myColor; 
}
</code></pre>

### Maps
##### With Sass Maps we can create multiple variables
<pre><code>
$colors: (
    primary: #4662ff,
    secondary: #abc123,
    accent: #f0fad4
);

body {
    background-color: map-get($colors, primary);
}
</code></pre>

### Sass funtions
##### Sass Functions allow you to define complex operations on SassScript values that you can re-use throughout your stylesheet
<pre><code>
@function color($color-name) {
    @return map-get($colors, $color-name);
}

body {
    background-color: color(primary);
}
</code></pre>

### Sass Mixin
##### Mixins allow you to define styles that can be re-used throughout your stylesheet.

<pre><code>
$desktop: 840px;

@mixin desktop {
    @media (min-width: #{$desktop}) {
        @content;
    }
}
</code></pre>

### Math is Sass
##### You can do math calculations in Sass

<pre><code>
$padding: 1rem;

padding: $padding $padding * 5;
</code></pre>

##### If parent and child class share the same name, the above can be written with an &-
<pre><code>
.showcase {
    background-color: $primary-color;

    .showcase-content {
        height: 100%;
    }
}

.showcase {
    background-color: $primary-color;

    &-content {
        height: 100%;
    }
}
</code></pre>

### Detecting BG clr to set TEXT clr

<pre><code>
@function set-text-color($color) {
    @if (lightness($color) > 70) {
        @return #333;
    }
    @else {
        @return #eee;
    }
}

.showcase {
    @include set-background($primary-color);
}
</code></pre>

### Each loops in Sass
##### Sass will create multiple classes based on the classnames used in HTML markup
<pre><code>
$spaceamount: (1, 2, 3, 4, 5);

@each $space in $spaceamount {
    .m-#{$space} {
        margin: #{$space}rem;
    }

    .my-#{$space} {
        margin: #{$space}rem 0;
    }

    .p-#{$space} {
        padding: #{$space}rem;
    }

    .py-#{$space} {
        padding: #{$space}rem 0;
    }
}
</code></pre>