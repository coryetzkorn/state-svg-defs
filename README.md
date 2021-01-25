# US State SVG Defs

This repo includes a few handy things:

+ A single state-svg-defs.svg file, providing easy access to all icons in one simple file.
+ SVG directory with individual SVG icons. (SVG defs approach recommended, but you could also include files from here individually).
+ Docs demonstrating svgdefs implementation.

## Demo
Check out the demo [here](https://coryetzkorn.github.io/state-svg-defs/).

## Usage

### Step 1 - Including the svgdefs file
Include the contents of `state-svg-defs.svg` in your HTML file. It needs to be included at the *top* of your document (or at least *before* you reference an icon). I recommend including it directly after the opening `<body>` tag.

Ways to include:

Copy the entire contents of `state-svg-defs.svg` and paste it after your document's opening `<body>` tag.

or

Copy the contents into a partial and include it after your document's opening `<body>` tag.
PHP: `<?php include('partials/state-svg-defs.php'); ?>`
Rails: `<%= render 'partials/state-svg-defs' %>`


### Step 2 - Referencing the svgdefs file

You've already done the hard part. Using the icons is super easy!

Paste this SVG xlink snippet where the icon should appear:

```html
<svg class="icon icon-state-MO">
  <use xlink:href="#icon-state-MO"></use>
</svg>
```

### Step 3 - Styling icons

For best results, include the following CSS in your main stylesheet:

```css
.icon {
  stroke-width: 0;
  stroke: currentColor;
  fill: currentColor;
}
```

Now you can style the icons easily by setting the `color` on their parent element.

For example, if the icon is wrapped in a div with a class of `.state` ...
```html
<div class="state">
  <svg class="icon icon-state-MO">
    <use xlink:href="#icon-state-MO"></use>
  </svg>
</div>
```

... you could make the icon red using the following css:

```css
.state {
  color: red;
}
```

... and you could animate the color on hover like this:

```css
.state {
  color: red;
  transition: 500ms color;
}
.state:hover {
  color: pink;
}
```
Easy!

## Credit
The original icons were [designed by ProPublica](https://github.com/propublica/stateface) and provided as an icon font.
I simply converted them to the (more modern) svgdefs format.
Kudos to ProPublica for the original work!

United States territory SVGs from [Wiki Commons](https://commons.wikimedia.org/wiki/File:Blank_USA,_w_territories.svg)

## Contributors
[coryetzkorn](https://github.com/coryetzkorn), [jomurgel](https://github.com/jomurgel)