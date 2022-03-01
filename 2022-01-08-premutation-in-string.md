---
layout: post
title: "Permutation in String"
date: "2022-01-08 20:59:03 -0700"
tags: [String, Hash Table, Sliding Window, Two Pointers]
level: Medium
---

# Problem

Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise.

In other words, return true if one of s1's permutations is the substring of s2.

 

### Example 1:

Input: s1 = "ab", s2 = "eidbaooo"

Output: true

Explanation: s2 contains one permutation of s1 ("ba").

### Example 2:

Input: s1 = "ab", s2 = "eidboaoo"

Output: false
 

### Constraints:

1 <= s1.length, s2.length <= 10^4

s1 and s2 consist of lowercase English letters.


# Solution

{% highlight js %}
/**
 * @param {string} s1
 * @param {string} s2
 * @return {boolean}
 */

var charMap = function(s) {
    let theMap = {};
    
    for (i=0; i<s.length; i++){
        if (s[i] in theMap) {
            theMap[s[i]]++
        } else{
            theMap[s[i]] = 1;
        }
    }
    
    return theMap;
}

function checkEqual(object1, object2) {
  const keys1 = Object.keys(object1);
  const keys2 = Object.keys(object2);
  if (keys1.length !== keys2.length) {
    return false;
  }
  for (let key of keys1) {
    if (object1[key] !== object2[key]) {
      return false;
    }
  }
  return true;
}

var checkInclusion = function(s1, s2) {
    
    let left = 0;
    let right = s1.length;
    
    let s1map = charMap(s1);
    
    while (right <= s2.length){
        let temp = "";
        temp = s2.slice(left, right);
        let tempMap = charMap(temp);

        if (checkEqual(s1map, tempMap)){
            return true;
        }
        left++;
        right++;
    }
    return false;
    
};
{% endhighlight %}

Runtime: 2328 ms, faster than 24.45% of JavaScript online submissions for Permutation in String.

Memory Usage: 62.4 MB, less than 5.12% of JavaScript online submissions for Permutation in String.