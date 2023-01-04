---
sidebar_position: 2
---

# HTML Element

An HTML Element component may be added to a form to display a single HTML element. This is useful if you wish to quickly insert and configure some HTML in your form. All unsafe HTML is stripped before rendering to prevent cross-site scripting exploits. This includes tags like `<script>`, `<embed>`, and `<style>`, and attributes like onmouseover or onload.

If you wish to insert more complicated HTML in your form, see the Content component

![HTML Element](img/html-component.png)

## HTML Tag

The name of the HTML tag to display.

## CSS Class

The CSS class to add to the HTML element. You may specify multiple classes by separating them with single spaces.

## Attributes

Attributes and their values to add to the HTML element. This is commonly used to add href attributes to `<a>` tags, or src attributes to `<img>` tags.

## Content

The text content of the HTML element. While adding more child HTML tags here will properly display them, it is recommended you use the Content component to easily write and preview more complex HTML.
