---
layout: post
title: "Total DOMination"
date: 2014-11-16 18:24:43 -0500
comments: true
categories: DOM
---

Last week at the Flatiron school, we took the dive into Javascript and jQuery to create more inactive and dynamic webpages. Javascript and jQuery interact with something called the DOM - the document object model. The DOM is a representation of HTML in a hierarchal tree-like structure, or an API for HTML. It allows javascript and jQuery to quickly find HTML elements. Every browser is able to generate a DOM, but how? Glad you asked…

The first thing we will need to construct the DOM is some HTML. 

{% codeblock lang:objc %}
<!DOCTYPE html>
<html>
<body>

<h1>Hello world</h1>

<p>Blah blah blah.</p>

</body>
</html>
{% endcodeblock %}

Upon receiving the HTML, the browser will tokenize, or convert strings into tokens. Adhering to the W3C HTML5 Standard, it will take strings inside brackets and create tokens, for example the `<html>` will be converted into an html token. Tokens look like: `start tag: html`,`start tag: body`, `start tag: h1`,`end tag: h1`, `start tag: p`, `end tag: p`,`end tag: body`, `end tag: html`. These tokens will be then converted into nodes by means of a lexer. A lexer is a type of parser. And from these nodes, a DOM tree will be constructed. The browser will be able to determine parents and children from the start and end tags. For example since the `start tag: body` is situated between the `start tag: html` and `end tag: html`, the browser will know that the `body` node is a child of the `html` node.

{% img /images/DOM_tree.png 1024 768 'DOM tree' 'DOM' %}
