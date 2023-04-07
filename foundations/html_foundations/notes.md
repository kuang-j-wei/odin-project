# Introduction to HTML and CSS
## Knowledge Check
* What do HTML and CSS stand for?
    * HTLM - hypertext markup language
    * CSS - Cascading Style Sheet

* Between HTML and CSS, which would you use for putting paragraphs of text on a webpage?
    * HTML
* Between HTML and CSS, which would you use for changing the font and background color of a button?
    * CSS
* What is the difference between HTML, CSS and JavaScript?
    * HTML creates the structure of a page
    * CSS stylizes the page
    * JavaScript allows for interactivity for your webpage

# Elements And Tags
Elements are like containers for content.

And tags tell browsers what content the element contains.

## Knowledge Check
> What is an HTML tag?

Objects that tell browsers what kind of content the element is.

> What are the three parts of an HTML element?

Opening tag, content, and closing tag.

# HTML Boilerplate
## Knowledge Check
* Q: What is the purpose of the doctype declaration?
    * A: To tell the browser what HTML version it uses. For HTML5, it should just be `<!DOCTYPE html>`

* Q: What is the HTML element?
    * A: It's the root element of the document. Every HTML document should have it. All other elements are descendants of it.

* Q: What is the purpose of the head element?

    * A: It's a meta element that has meta information about the webpage. For example, what character set to use. It should not include any content of a web page in this element.
        * `<title></title>` Should also be included. It will be displayed on the tab in browser.

* What is the purpose of the body element?
    * A: Content that is displayed to users is put here.
    * It's inside the `<html>` element and goes below the `<head>` element

# Working with Text
## Knowledge Check
* Q: How do you create a paragraph in HTML?
    * A: `<p></p>` tag
* Q: How do you create a heading in HTML?
    * `<h1></h1>` and it goes all the way to `<h6></h6>`
* Q: How many different levels of headings are there and what is the difference between them?
    * 6
* Q: What element should you use to make text bold and important?
    * `<strong></strong>`
* Q: What element should you use to make text italicized to add emphasis to it?
    * `<em></em>`
* Q: What relationship does an element have with any nested elements within it?
    * Parent-child
* Q: What relationship do two elements have if they are at the same level of nesting?
    * Sibilings
* Q: How do you create HTML comments?
    * `<!-- -->`

# Lists
## Knowledge Check
* Q: What HTML tag is used to create an unordered list?
    * `<ul></ul>`
* Q: What HTML tag is used to create an ordered list?
    * `<ol></ol>`
* Q: What HTML tag is used to create list items within both unordered and ordered lists?
    * `<li></li>`

# Links and Images
## Knowledge Check
* Q: What element is used to create a link?
    * `<a><\a>` anchor (needs an `href` attribute to actually make the link work)
* Q: What is an attribute?
    * Gives additional information to an HTML element
* Q: What attribute tells links where to go to?
    * `href`
* Q: What is the difference between an absolute and relative link?
    * Absolute is the full path to a page
    * Relative link tells you the path, starting from your main domain
* Q: Which element is used to display an image?
    * `<img>`
    * Note that there is no closing tag for `<img>`
* Q: What two attributes do images always need to have?
    * `src` and `alt`
* Q: How do you access a parent directory in a filepath?
    * Use `../`
* Q: What are the four main image formats that you can use for images on the web?
    * JPEG
    * PNG
    * GIF
    * SVG

# Commit Messages
## Knowledge Check
* What are two benefits of having well-written commit messages and a good commit history?
    * Improve maintainability
    * Provides context of why a change happened and what was done
* How many characters should the subject line of your commit message be?
    * 50