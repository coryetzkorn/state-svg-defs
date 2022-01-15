# US State SVG Defs

This repo includes a few handy things:

+ A single state-svg-defs.svg file, providing easy access to all icons in one simple file.
+ SVG directory with individual SVG icons. (SVG defs approach recommended, but you could also include files from here individually).
+ This `readme` demonstrating svgdefs implementation.

## Demo
Check out the demo [here](https://coryetzkorn.github.io/state-svg-defs/).

## Usage

### Step 1 - Including the svgdefs file
Copy the `state-svg-defs.svg` file into your HTML project, e.g. in an `./svg` folder.

### Step 2 - Referencing the svgdefs icons

Paste this SVG xlink snippet where the icon should appear:

```html
<svg class="icon state-icon">
    <use xlink:href="svg/state-svg-defs.svg#icon-state-MO"></use>
</svg>
```

If you used a different location for the file, replace `svg` with the path you used. To refernce a state other than Missouri, replace `MO` with the appropriate 2-letter abbreivation. Use `USA` for the full continental United States.

### Step 3 - Styling icons

Include the following CSS in your main stylesheet:

```css
.icon {
  stroke-width: 0;
  stroke: currentColor;
  fill: currentColor;
}

.state-icon {
    display: inline;
    height: 3rem;
}
```

### Step 4 - Color-Coding icons

Now you can style an icon easily by setting the `color` on its parent element.

For example, you can make the icon settable to red or blue using the following css:

```css
.red-state {
  color: red;
}

.blue-state {
  color: blue;
}
```

You can apply a hover effect using the following css:

```css
.red-state:hover {
  color: pink;
  transition: 500ms color;
}
.blue-state:hover {
  color: lightblue;
  transition: 500ms color;
}
```

To mark a state icon as a "red state", the icon's parent element is wrapped in a div with the class of `red-state`.

```html
<div class="red-state">
  <svg class="icon state-icon">
    <use xlink:href="svg/state-svg-defs.svg#icon-state-MO"></use>
  </svg>
</div>
```

Easy!

## Credit
The original icons were [designed by ProPublica](https://github.com/propublica/stateface) and provided as an icon font.  
I simply converted them to the (more modern) svgdefs format.  
Kudos to ProPublica for the original work!