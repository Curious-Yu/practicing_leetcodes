---
layout: post
title: "Reverse String"
date: "2022-01-01 16:59:03 -0700"
tags: [String, Two Pointers, Recursion]
level: Easy
---

# Problem

Write a function that reverses a string. The input string is given as an array of characters `s`.

You must do this by modifying the input array in-place with O(1) extra memory.

 

### Example 1:

Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]

### Example 2:

Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
 

### Constraints:

1 <= s.length <= 10^5
`s[i]` is a printable ascii character.

# Solution

{% highlight js %}
/**
 * @param {character[]} s
 * @return {void} Do not return anything, modify s in-place instead.
 */
var reverseString = function(s) {
    
    let low = 0;
    let high = s.length-1;
    let count = 0;
    
  
    while (low <= high){
        s.push(s[high]);
        count++;
        high--;
    }
    
    s.splice(low, count);
    
    
    return s;
    
};
{% endhighlight %}

Runtime: 177 ms, faster than 8.78% of JavaScript online submissions for Reverse String.

Memory Usage: 46.8 MB, less than 13.30% of JavaScript online submissions for Reverse String.