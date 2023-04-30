# Introduction to Flexbox
Flex container, an element that has `display: flex` on it.

```
.containre {
    display: flex;
}
```


Inside are flex items. They have to be direct descendants of the container. They are items that are inside a flex container.

A flex item itself can be made into a flex container as well.

## Knowledge Check
* What’s the difference between a flex container and a flex item?
    * Flex item lives inside flex container. Flex containers are simply elements that contains flex items.
* How do you create a flex item?
    * By defining `display: flex`
# Growing and Shrinking
`flex: 1` property means:
* `flex-grow`: `1`. Single number. Growth factor, relative to other flex items.
  * By default, each element will shrink down to their minimum comfortable sizing
  * Without specifying `flex: 1`, the default is `0`
  * If more than one item is non-zero, then we will divide up the available space relative to the growth factor weighting
  * It determines how _extra space is distributed_
* `flex-shrink`: `1`. Single number. Shrink factor relative to other flex items.
  * The default is also `1` without specifying `flex: 1`
  * `flex-shrink: 0` would make an item to not shrink.
  * The ratio between child items are what matter, not the absolute numbers
  * Given a certain amount of pixel deficit, the item with the larger `flex-shrink` will pay a higher portion of the deficit
  * It determines how _extra space is removed_
* `flex-basis`:`0%`. Single number. It sets the initial size of a flex item.
  * It sets the hypothetical size of the primary axis
  * It also sets the minimum size, since item can't be below this threshold
* Note that often many types of content has a predefined minimum width
  * For example for texts it's 170px-200px
  * We can set the `min-width: 0px` so that the child content can `flex-shrink` according to the parent container 

## Common Shorthands
* `flex: initial` = `flex: 0 1 auto`
    * Size based on width/height properties
    * Don't fill positive free space
    * Allow to shrink to minimum size when there's insufficient space
* `flex: auto` = `flex: 1 1 auto`
    * Size based on width/height properties
    * Fill positive free space
    * Allow to shrink to minimum when insufficient space
* `flex: none` = `flex: 0 0 auto`
    * Initial width/height
    * Fully inflexible, even in overflow situations
* `flex: <positive-number>` = `flex: 1 1 0`
    * Items use specified proportions of the free space (i.e. based on content width)
![](https://www.w3.org/TR/css-flexbox-1/images/rel-vs-abs-flex.svg)

## flex-basis `auto` vs `0`
* `0` grows from the content
* `auto` grows from the specified `width` and `height` of the flex item.


## Knowledge Check
* What are the 3 values defined in the shorthand flex property (e.g. flex: 1 1 auto)?
    * `flex-grow`: control the proportion/speed relative to others in which the item grows. Initial value is `0`
    * `flex-shrink`: like grow, but in the shrink direction. Initial value is `1`.
    * `flex-basis`: The starting point in which the flex item grows. Initial value is `auto`.
* What are the 3 defined values for the flex shorthand flex:auto?
    * `inital` - `0 1 auto`
    * `auto` - `1 1 auto`
    * `none` - `0 0 auto`

# Axes
* Main axis
* Cross axis
* `flex-direction: column`: top to down
* `flex-direction: row`: left to right

## Knowledge Check
* How do you make flex items arrange themselves vertically instead of horizontally?
    * `flex-direction: column`
* In a column flex-container, what does flex-basis refer to?
    * `height`
* In a row flex-container, what does flex-basis refer to?
    * `width`
* Why do the previous two questions have different answers?
    * Because the main axis is different now


# Alignment
## Main Axis
* `justify-content` - justify all items in a container
    * `flex-start`
        * Default
        * Starts from the start with no space between container and item, and between items
    * `flex-end`
        * Like `flex-start`, but start from the end
    * `space-around`
        * Have space between the container and items
        * Also space between items
        * The space between items are the same, and the spaces don't "absorb", meaning neighbors would double the space
    * `space-between`
        * No space at the ends
        * Only space between items
    * `space-evenly`
      * Similar to `space-between`, except that the neighboring items' spaces absorb
    * `center`
        * All centered
        * No space between items

## Cross Axis
* `align-items` - align all items in a container
    * `stretch`
        * Default
        * Stretch to however big the container is
    * `flex-start`
        * Start from the top
        * Only take up as much space as the content of the items needed
    * `center`
        * Center within the cross axis
* `align-self` - align an item in a container

## Item in an Container
* `align-self` - justify/align an item in a container
    * It's applied to just a specific child of a flex container
    * `align-items` is just `align-self` except it's automatically applied to every child item


## Gap
* To add gaps between items, in `.container` add `gap: 8px`
    * It creates space in-between each Flex child

## Margin
* Add space aroun a specific child element
* Default is `0`
* Margin will gobble up the extra space if set to `1`

## Wrapping
* Setting `flex-wrap: wrap` on the container, items won't shrink below their hypothetical size