---
layout: post
title: "Single Number 2"
date: "2021-05-20 22:18:27 -0700"
tags: [Array, Bit Manipulation]
level: Easy
---

# Problem

Given a non-empty array of integers `nums`, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

Example 1:

`Input: nums = [2,2,1]`

Output: 1

Example 2:

`Input: nums = [4,1,2,1,2]`

Output: 4

Example 3:

`Input: nums = [1]`

Output: 1

Constraints:

1. -1 <= nums.length <= 3 * 104

2. -3 * 104 <= nums[i] <= 3 * 104

Each element in the array appears twice except for one element which appears only once.

# Solution

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
    let result = 0;
    for(let i=0; i<nums.length; i++){
        result = result ^ nums[i];
    }
    return result;
};
{% endhighlight %}

# Note

![XORbitwise](/pic/XORbitwise.PNG)

From: https://www.w3schools.com/js/js_bitwise.asp
