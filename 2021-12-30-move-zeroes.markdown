---
layout: post
title: "Move Zeroes"
date: "2021-12-30 17:59:03 -0700"
tags: [Array, Two Pointers]
level: Easy
---

# Problem

[30-Day LeetCoding Challenge for April 2020](https://leetcode.com/explore/challenge/card/30-day-leetcoding-challenge/)

Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

Example:

`Input: [0,1,0,3,12]`

Output: [1,3,12,0,0]

Note:

1. You must do this in-place without making a copy of the array.

2. Minimize the total number of operations.

### Hint#1

In-place means we should not be allocating any space for extra array. But we are allowed to modify the existing array. However, as a first step, try coming up with a solution that makes use of additional space. For this problem as well, first apply the idea discussed using an additional array and the in-place solution will pop up eventually.

### Hint#2

A two-pointer approach could be helpful here. The idea would be to have one pointer for iterating the array and another pointer that just works on the non-zero elements of the array.

# Solution - loops

{% highlight js %}

/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    let j = 0;
    let i = 0;
    while (i < nums.length){
        if (nums[i]!==0){
            nums[j] = nums[i]
            j++;
        }
        i++;
    }
    console.log(i);
    console.log(j);
    console.log(nums);

    while (j < nums.length){
        nums[j]=0;
        j++;
    }

    return nums;
};

{% endhighlight %}

Runtime: 92 ms

Memory Usage: 38.8 MB

# Solution - two pointers

{% highlight js %}
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    
    let i = nums.length-1;
    
    while (i > -1){
        if (nums[i] === 0){
            nums.splice(i,1);
            nums.push(0);
        }
        i--;
        
    }
    
    return nums;
};
{% endhighlight %}

Runtime: 161 ms, faster than 15.21% of JavaScript online submissions for Move Zeroes.

Memory Usage: 43.3 MB, less than 89.66% of JavaScript online submissions for Move Zeroes.