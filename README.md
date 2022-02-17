# Sass (scss) Tutorial
___

#### We link the regular CSS style sheet file (.css) in the HTML file, and we make and name an SCSS (.scss) style sheet file. Live Sass compiler extention of VS Code compiled .scss file into regular .css after clicking on "watch Sass" button on the bar at the bottom.

#### Live sass compiler extension created 2 css file. css.map file we don't need to worry about, but in regular .css style file we shouldn't make any changes because those will be overwritten with any saved changes in Sass (scss) file.

## Sass variables, Sass maps, Nesting in Sass, Sass funtions, Sass Mixins

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
@mixin desktop {
    @media (min-width: #{$desktop}) {
        @content;
    }
}
</code></pre>