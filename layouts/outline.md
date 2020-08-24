# CSS Layouts

## Flexbox

### What is Flex For?

* describing content flow
* light minimal layouts
* unidirectional descriptions

### Components of Flex

* main axis
* cross axis
* flex container
* flex items

### Flex Flow

* flex-direction: sets the main axis, default is horizontal
* flex-wrap: sets the item reflow order
* flex-flow: combines the two

### Item Layout

* justify-content: works on the main axis
    * flex-start, flex-end, center
    * safe, unsafe
* align-items: works on the cross axis

* difference between align-items and align-content
* relationship between justify-content and align-content

### Flex Items

* order
* flex-grow: proportional size of a flex-item
* flex-shrink: ability for a flex-item to shrink relative to it's peers
* flex-basis: default size of an element before space distribution

*** use flex + order ***

## Grid

### Starting with Implicit Grids

* grid-auto-flow
* grid-auto-columns
* grid-auto-rows

### Setting Up Spacing

* row-gap
* column-gap
* gap

**only set up between grid spaces**

### Grid Alignment

* justify-content: row
* align-content: column
* place-content: sets both in a single declaration

### Grid Item Alignment

* justify-items: row
* align-items: column
* place-items

### Laying out Grids

* grid-template-rows
* grid-template-columns
* grid-template-areas
* grid (only implicit or explicit declarations)

### Grid Items

* grid row
* grid column
* grid area
* place self: same as align / justify items
    * align self
    * justify self

### Grid Layout Concerns

* fr and static sizes
* auto
* .
* [label1], [label1-end label2-start]
* repeat
* minmax and auto
* referencing the nth labeled line in `grid-area`
* auto-fill: creates enough rows / columns to fill grid
* auto-fit: creates as many rows / columns as needed

## When to Use Grid vs Flex

* Use flexbox when the layout is strongly implied by content flow
* Use grid for more complex layouts and content placement

## Responsive Design

### Mobile Duck Typing

```css
@media (hover: hover) {}
@media (pointer: coarse) {}
```

### Overriding Styles with Media Queries

*** Start with the smallest collapse and build from there ***

```css
body {

}
```

```css
@media only screen and (min-width: 768px) {
 ...
}
```

### Media Query Strategies

* target at little as possible: just grid definition
* consider class stacking with a unique classname for each screen size
* use as few media queries as needed

### Where to Put a Media Query

* use the media attribute to defer css loading
* the challenge of mobile first (min-width vs max-width)
* why mobile first

### Some Recommended Media Queries

```css
/* Larger than phone */
@media (min-width: 600px) {}

/* Larger than tablet */
@media (min-width: 750px) {}

/* Larger than desktop */
@media (min-width: 1000px) {}

/* Larger than Desktop HD */
@media (min-width: 1200px) {}
```

## Q & A

Questions, Comments, Closing Thoughts?
