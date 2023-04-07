# CSS Foundations
## Basic Syntax
* Selector
* Property
* Value
## Selectors
* Universal Selector
    * `*`
* Type Selector
    * `type-name` i.e. `div`
    ```
    div {
        color: white;
    }
    ```
* Class Selectors
    * `.class-name`
    * Class is an attribute you place on an HTML element
    * i.e.
    ```
    <div class="alert-text">
        Place some content here
    </div>
    ```
    * Multiple classes can be added, by separating them with a white space
* ID Selectors
    * `#id-name`
    * ID is an attribute you place on an HTML element
    * i.e.
    ```
    <div id="title">
        Page title
    </div>
    ```
    * Each element can only have **one** ID
* Grouping Selector
    * Shared selectors can be placed together like so
    ```
    selector-1,
    selector-2 {
        property1: value1;
        property2: value2;
    }

    selector1 {
        /* unique selector-value */
    }

    selector2 {
        /* unique selector-value */
    }
    ```
* Chaining Selector
    * `selector1selector2`
    * Will only apply to elements that satisfy both classes
    * i.e. `.subsection.header` for `<div class="subsection header"></div>`
    * Works with class and ID selectors
    * Can't chian type selectors, because an HTML element can't be two different types at once
* Descendant Combinator
    * `.ancestor .child`, class selectors separated by a space
    * i.e.
    ```
    <div class="ancestor"> <!-- A -->
        <div class="contents"> <!-- B -->
            <div class="contents"> <!-- C -->
            </div>
        </div>
    </div>
    ```
    ```
    .ancestor .contents {
        property: value;
    }
    ```
    Then only `B` and `C` will be selected because they are descendants of `ancestor`

## Common Properties
* `font-family`: Best to provide a comma separated list like `font-family: "Times New Roman", sans-serif;`
* `font-size`
* `font-weight`
* `text-align`
* `height` and `width` for `img` (can use `auto` for one to not lose proportion)

## The Cascade of CSS
### Specificity
([Specific Examples](https://www.theodinproject.com/lessons/foundations-css-foundations#the-cascade-of-css))
* A more specific CSS declaration takes precedence
* Inline style goes first over selectors
* Among selectors
    1. ID
    2. Class
    3. Type
    * If tye types os selectors tie, then number determines it

### Inheritance
* For typography based properties, usually the children inherit from parents
* Most other properties don't inherit
* If a child is specified, then that takes priority
    * It can be targeted with a class selector, doesn't have to be ID

### Rule Order
* If both styles are tied, then the last declared gets applied (see [example](https://stackoverflow.com/questions/13539477/how-does-css-handle-specificity-tie))

## Adding CSS to HTML
### External CSS
* Most common
* Add `.css` file to HTMl
    ```
    <head>
      <link rel="stylesheet" href="styles.css">
    </head>
    ```
* `rel` attribute is necessary. It specifies the relationship between the HTML and the linked file

### Internal CSS
* Uuse a `<style></style>` tag inside of `<head></head>`

### Inline CSS
* Directly add a `style` attribute to an HTML element
* i.e. `<div style="color: white; background-color: black;">...</div>`

## Knowledge Check
* What are the main differences between external, internal, and inline CSS?
    * External: defines it in the `<head>` section of HTML via `<link rel="stylesheet" href="location>`. It uses a separate CSS file and link it to your HTML
    * Internal: defines CSS inside HTML in the `<head>` section with `<style>` tag. The CSS only applies to this particular HTML file
    * Inline: Directly define CSS to a single HTML element.
* What is the syntax for class and ID selectors?
    * Class: `.`
    * ID: `#`
* How would you apply a single rule to two different selectors?
    * You can group them together, where the two selectors are on two lines and separated by `,`
* Given an element that has an id of `title` and a class of `primary`, how would you use both attributes for a single rule?
    * Chain them as so: `.primary#title`
* What does the descendant combinator do?
    * Ensure that a rule only gets applied if the child is a descendant of a specified parent. The syntax is that the descendant and parent are separated by a single space ` `. Can be used for type, class, or ID.
* Between a rule that uses one class selector and a rule that uses three type selectors, which rule has the higher specificity?
    * Class will win, because it's more specific
    * The "three" types can be done via chaining or dependent-parent

# Inspecting HTML and CSS
## Knowledge Check
* How do you select a specific element on your page with your browser’s developer tools?
    * Right click and hit `inspect`
* What does a strikethrough in a CSS element mean in your browser’s developer tools?
    * The CSS rule is being overwritten.
* How do you change CSS in real time on specific elements of a web page with your browser’s developer tools?
    * Use the `Styles` pane in the bottom right
# The Box Model
## Main Concepts
* Everything on a webpage is a box

To manipulate the boxes, there are three concepts
* `margin`: The outside. Increase the space between a box and any others around it
    * Use this to space out two boxes
    * Will still add on top of the container's padding
* `padding`: The inside. Increases the space between the edge and the content
* `border`: The border. Adds space between the margin and padding

## Sizing Accounting
* The height and width are `height + 2 * (padding + border)` (`margin` is not included)
* If you want your entire box to be the size specified by `height` and `width`, then you define `box-sizing: border-box`
    * This would make the actual content of size `height - 2 * (padding + border)`
* It's common practice to add `box-sizing: border-box` to the universal selector `*` so that all boxes are the size of what's defined.
    ```
    * {
        box-sizing: border-box;
    }
    ```

## `display` property
* `display: block` new line and a box by itself
* `display: inline` no new line. Box is in line around it. `width` and `height` are ignored. Horizontal paddings, margins, and borders move other content away from the box. But doesn't change the vertical overlap.
* `display: flex`: The outer is `block` but the inside is `flex`. Default layout is horizontal.
* `display: inline-flex`: The outer box is blended as inline with other elements. The inside is `flex`.
* `display: inline-block`: Outer box is inline. But the inside is block (new line).`width` and `height` are respected.

## `auto` and centering
* If you specify a `width`, then setting `auto` to horizontal `margin` will fill your width
* You can set it to just one side of your horizontal margin, that will fill all space on that side

## Knowledge Check
* From inside to outside, what is the order of box-model properties?
    * Margin, border, padding
* What does the box-sizing CSS property do?
    * It allows `height` and `width` to be directly respected
    * The actual content size will be `height` and `width` minus `border` and `padding`
* What is the difference between the standard and alternative box model?
    * Standard: actual size is `width` + 2 * (`padding` + `border`)
    * Alternative: actual size is `width`
* Would you use margin or padding to create more space between 2 elements?
    * Margin
* Would you use margin or padding to create more space between the contents of an element and its border?
    * Padding
* Would you use margin or padding if you wanted two elements to overlap each other?
    * Margin
# Block and Inline
* Block
    * Each element is on a new line
    * By default spans the entire width of the parent element
    * Examples: `<p>`, `<div>` (divide)
* Inline
    * Sit on the same line along with adjacent text
    * Only take up as much width as necessary
    * You can't set `width` or `height` to inline elements.
    * `padding` is respected top and bottom, but can overflow to other lines
    * Examples: `<span>`
* inline-block
    * `width` and `height` can be set
    * Top and bottom margins and paddings are respected, without overflow
    * Still sits with other elements, just like an `inline` element (unlike `block`)

## Knowledge Check
* What is the difference between a block element and an inline element?
    * Block starts a new line. Inline blends with neighboring elements
* What is the difference between an inline element and an inline-block element?
    * Inline-block respects width and height and the padding will not overflow.
    * Inline width and height aren't enforced. Padding will overflow
* Is an h1 block or inline?
    * Block
* Is button block or inline?
    * Inline
* Is div block or inline?
    * Block
* Is span block or inline?
    * Inline