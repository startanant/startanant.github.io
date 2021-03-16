---
layout: post
title:  "A needle in a haystack: Part I"
date:   2019-09-25 17:33:46 -0400
categories: tech
tags: python javascript programming
---

Why would someone hide a needle in a haystack? That answer is out of the scope of this tutorial. Just know that the haystack is out there and sometimes the thing you need is the needle; and sometimes, you're the needle. Too much? Let's stick to the task at hand.

Our mission is to check if an element (we'll call it a "needle" for the purposes of this tutorial) is present in an array (we'll label it "haystack"). 

`haystack = ['h','e','l','l','o']`

We refer to each element by its position in the array. For example,

`haystack[1] = e`

Here's a simple function in JavaScript to find one needle (a letter) in a haystack (a word).

```javascript

function inArray(needle, haystack) {
	var count = haystack.length;
	for(var i = 0; i < count; i++) {
		if(haystack[i] === needle) {
			return true;
		}
    }
    return false;
}

```

You can try this out in the Chrome [REPL](https://developers.google.com/web/tools/chrome-devtools/console#javascript).
First, run the function and then call it by providing the parameters, where the first parameter is a "needle" of your choice and the second parameter is the "haystack" we defined earlier.

```
> inArray('e',haystack)
< true
> inArray('x',haystack)
< false
```

An `includes()` method that is now standard in [ECMAScript 2016](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) does the same thing - "determines whether an array includes a certain value among its entries". Or, in plain English, looks for a needle in a haystack.

```
> haystack.includes('a')
< false
> haystack.includes('e')
< true
```

If you wish to read the next post in the series, click [A needle in a haystack: Part II]({{site.url}}tech/2019/09/30/find-needles-2.html)
