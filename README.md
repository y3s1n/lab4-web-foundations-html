# lab4-web-foundations-html
COMP 305 Fall 2025 

## Validator Issues

<optgroup> in a <datalist>: returns an error because <datalist> can only contain <option> elements, not grouping elements.

<label> as a child of <option>: returns an error because <option> is a phrasing element that can only contain text and labels cannot go inside options.

<colgroup> inside <tr>: returns an error because <colgroup> must be placed directly inside <table> before <thead>, <tbody>, or <tr>, not inside a row.

## HTML Element Notes

<address> is a block-level element and will always create a new line.

Description list (<dl>):

<dt>: description term

<dd>: description detail

<div>: A generic container with no meaning. Use when grouping for styling/structure only.

<section>: A semantic container that represents a standalone thematic part of a document, should have its own heading. Improves accessibility.

<article>: A self-contained, independent block of content that could stand alone, be distributed, or republished elsewhere. Should have its own heading.

## Base Href Issue

Using <base href="https://www.sandiego.edu/"> caused every relative link to be prefixed with the USD domain.

This worked for links that were actually on the USD site (e.g., <form action="/search">, <a href="about/history.php">).

But it broke local links like images, because those links were also prefixed with the USD domain.

One attempted fix was to use an absolute local URL such as:

<img src="http://127.0.0.1:5500/lab4-web-foundations-html/docs/validation-fail.png">


However, this would be restricted to my local host and a machine using a different port would not be able to displaly the image

The final solution: remove href from <base> but keep target="_blank".

that way links open in new pages rather than the html one, and links wont be prefaced with the usd domain.
