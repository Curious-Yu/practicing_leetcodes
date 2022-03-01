---
layout: post
title: "Longest Substring Without Repeating Characters"
date: "2022-01-03 20:59:03 -0700"
tags: [String, Hash Table, Sliding Window]
level: Medium
---

# Problem

Given a string s, find the length of the longest substring without repeating characters.

 

### Example 1:

Input: s = "abcabcbb"

Output: 3

Explanation: The answer is "abc", with the length of 3.

### Example 2:

Input: s = "bbbbb"

Output: 1

Explanation: The answer is "b", with the length of 1.

### Example 3:

Input: s = "pwwkew"

Output: 3

Explanation: The answer is "wke", with the length of 3.

Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
 

### Constraints:

0 <= s.length <= 5 * 10^4

s consists of English letters, digits, symbols and spaces.

# Solution

{% highlight js %}
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLongestSubstring = function(s) {
    
    let i = 0, j = 0, max = 0
    let set = new Set()
    
    while(i < s.length) {
        if (set.has(s[i])) {
            set.delete(s[j++])
        } else {
            set.add(s[i++])
            max = Math.max(max, set.size)
        }
    }
    
    return max
    
};

{% endhighlight %}

Runtime: 214 ms, faster than 31.20% of JavaScript online submissions for Longest Substring Without Repeating Characters.

Memory Usage: 42.8 MB, less than 82.97% of JavaScript online submissions for Longest Substring Without Repeating Characters.
