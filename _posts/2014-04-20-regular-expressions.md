---
layout: post
title: "Regular Expressions"
modified: 2014-04-20 13:22:37 -0400
tags: [RegEx, Ruby, Syntax]
image:
  feature: 
  credit: 
  creditlink: 
comments: true
share: true
---

# What is a Regular Expression?

In programming languages, a regular expression is a pattern that can be matched against a string. The origins of the term Regular Expression go back to a language classification when linguist Noam Chomsky developed a model to classify languages according to a given set of rules. These included regular languages, context free languages, context-sensitive languages, and recursively enumerable languages. Mathematician Stephen Kleen further formalized concept of Regular Expressions for programming languages and Unix. 

So.. What is a regular language?

Imagine you have an abstract machine made of lego. Our lego machine can run through a finite number of states for a given operation to produce a unique computation. A regular language, then is a language that can pass through this our lego machine, which we’ll call a Finite State Machine. Similarly combination locks that had a finite amount of memory or a fixed number of states (right, left, and down). If we input a strings of numbers, the set of strings that could passed would be regular language. And all Regular Languages contain Regular Expressions.

Though this is a little abstract, for our purposes Regular Expressions in programming are used to read data files and parse through specific data that we want to add or omit. There a some version of a regular expressions in every programming language, such as Javascript, Java, C#, and, lucky for us, the Ruby language has built in Regular Expression capabilities.

# Common Types of Regular Expressions

We’ll focus on four broad categories of Regular Expressions including Anchors, Characters and Whitespaces, Character Classes and Subexpression Modifiers. Though a variety of methods like gsub, match, split, can be used with Regular Expressions, we’ll be using the scan method to get a basic understanding of how the above categories really work.

Sound fun? Let’s try it!

# Anchors

Anchors, allows us to search for or return a part of its string based on its location. 

{% highlight ruby %}
^  Anchor for the beginning of a line
$  Anchor for the end of a line
\  Anchor for the start of a string
\Z Anchor for the end of a string 
{% endhighlight %}

So if we had the following string:

{% highlight ruby %}
yoda = ‘Remember. A Jedis strength flows from the Force.'
{% endhighlight %}

We can use the Regular Expressions as anchors as seen below:

{% highlight ruby %}
yoda.scan(/^.../)  #returns three characters from the beginning
=> ["Rem"] 
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/……\Z)   #returns six characters from the end 
=> [“Force.”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/……….$/) #returns ten characters from the end of the current 
line
=> [“the Force.”]
{% endhighlight %}

# Characters and Whitespaces

Regular Expressions for characters and whitespaces allow us to match a character, a digit, a whitespace, or an underscore against a given string.

Here are some of the most helpful of these expressions:

{% highlight ruby %}
. Any character
\w Any letter, digit, or underscore
\W Anything that \w doesn’t match
\d Any digit
\D Anything that D doesn’t match 
\s Whitespaces 
\S Nonwhitespaces 
(a|b) a or b
{% endhighlight %}

So if we had the following yoda string:

{% highlight ruby %}
yoda = ‘Ready are you? What know you of ready? For 800 years have I 
trained Jedi.’
{% endhighlight %}

We could do a scan for virtually any character in the string we want to return:

{% highlight ruby %}
yoda.scan(/\d+/)    #returns all digits 
=> [“800”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/\d/)     #returns all single digits
=> [“8”, “0”, “0”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/\s|\d/)  #returns all whitespaces and digits
=> [” “, ” “, ” “, ” “, ” “, ” “, ” “, ” “, ” “, “8”, “0”, “0”, ” “, 
” “, ” “, ” “, ” “]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/\w/)     #returns all characters that are not whitespaces
=> [“R”, “e”, “a”, “d”, “y”, “a”, “r”, “e”, “y”, “o”, “u”, “W”, “h”, “a”, “t”, “k”, “n”, “o”, “w”, “y”, “o”, “u”, “o”, “f”, “r”, “e”, “a”, “d”, “y”, “F”, “o”, “r”, “8”, “0”, “0”, “y”, “e”, “a”, “r”, “s”, “h”, “a”, “v”, “e”, “I”, “t”, “r”, “a”, “i”, “n”, “e”, “d”, “J”, “e”, “d”, “i”]
{% endhighlight %}


# Character Classes

Character classes allow you to match a specific set of characters. So if we had the following string:

{% highlight ruby %}
yoda = ‘You must unlearn what you have learned.’
{% endhighlight %}

We could scan the string for the following classes of characters:

{% highlight ruby %}
yoda.scan(/[aeiou]/)  #returns all vowels 
=> [“o”, “u”, “u”, “u”, “e”, “a”, “a”, “o”, “u”, “a”, “e”, “e”, “a”, “e”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/[^aeiou])  #returns anything that is not a vowel 
=> [“Y”, ” “, “m”, “s”, “t”, ” “, “n”, “l”, “r”, “n”, ” “, “w”, “h”, “t”, ” “, “y”, ” “, “h”, “v”, ” “, “l”, “r”, “n”, “d”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/[A-Z]/)    #returns all capital letters from A-Z 
=> Y
{% endhighlight %}


# Subexpression Modifiers

Subexpression modifiers allow us to match the occurrences of a specific character. 

{% highlight ruby %}
b+  Scan for one or more instances of b 
b* Scan for zero or more instances of b
b+? Scan for one or more instance of b, as few as possible
book? Scan for the exact string before the ?
b{a} Scan for a instances of b  
{% endhighlight %}

Here’s our yoda string again: 

{% highlight ruby %}
yoda = 'In a dark place we find ourselves, and little more knowledge lights our way.'
{% endhighlight %}

And here we use the following Regular Expressions to parse through our code:

{% highlight ruby %}
yoda.scan(/t+/)     #returns all instances of ts 
=> [“tt”, “t”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/a{1,6}/) #returns all a’s from a number of 1-6 
=> [“a”, “a”, “a”, “a”, “a”, “a”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/ittle?/) #returns all ‘ittle’ 
=> [“ittle”]
{% endhighlight %}

{% highlight ruby %}
yoda.scan(/ittle?|ind?/) #returns all inds or ittles 
=> [“ind”, “ittle”]
{% endhighlight %}

Fun, Right?

Finally, I leave you with a a cool video, a lego version of the Turing Machine, known as the first computer.

<iframe width="500" height="230" src="//player.vimeo.com/video/44202270" frameborder="0"> </iframe>