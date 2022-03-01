---
layout: post
title: "Reverse Words in a String III"
date: "2022-01-01 18:59:03 -0700"
tags: [String, Two Pointers]
level: Easy
---

# Problem

Given a string `s`, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

 

### Example 1:

Input: s = "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"

### Example 2:

Input: s = "God Ding"
Output: "doG gniD"
 

### Constraints:

1 <= s.length <= 5 * 10^4
`s` contains printable ASCII characters.
`s` does not contain any leading or trailing spaces.
There is at least one word in `s`.
All the words in s are separated by a single space.

# Solution

{% highlight js %}
/**
 * @param {string} s
 * @return {string}
 */
var reverseWords = function(s) {
    
    s = s.split(" ");
    let newArray = [];
    
    for ( i of s){
        i = i.split("").reverse().join("");
        newArray.push(i);
    }

    return newArray.join(" ");
};
{% endhighlight %}

Runtime: 99 ms, faster than 26.36% of JavaScript online submissions for Reverse Words in a String III.

Memory Usage: 45.7 MB, less than 21.28% of JavaScript online submissions for Reverse Words in a String III.