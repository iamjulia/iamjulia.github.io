---
layout: post
title: "Gimme Some Syntactic Sugar"
date: 2014-10-15 23:08:44 -0400
comments: true
categories: "Syntactic sugar"
---

As a beginner programmer, learning a new language can be scary and daunting. So, I was delighted to learn about "syntactic sugar". 

The term "syntactic sugar" sounds sweet and inviting, and it is! It is syntax that does not follow the regular conventions and it makes for easier writing and reading of code. Ruby was designed with it's users in mind so its syntax is rather natural and not much different from the way we actually speak at times. Syntactic sugar makes Ruby (and other languages) more user (and beginner) friendly!

Life with no sugar...

{% codeblock lang:objc %}
2.+(5)
x=x+1
"hello world".send(:capitalize)
a||a=b
{% endcodeblock %}

A spoon full of sugar helps the code look much prettier...

{% codeblock lang:objc %}
2+5
x+=1
"hello world".capitalize
a||=b
{% endcodeblock %}

Wow, look how much clearer and "more human" the code looks with a touch of sugar!

Unfortunately, not everyone is a fan of syntactic sugar. There are critics that see these exceptions as rather unimportant.

"Syntactic sugar causes cancer of the semicolon." - Alan Perlis

{% img http://i2.kym-cdn.com/photos/images/facebook/000/184/700/1318369988001.jpg %}
