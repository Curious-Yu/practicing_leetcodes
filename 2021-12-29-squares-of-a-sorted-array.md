---
layout: post
title: "Squares of a Sorted Array"
date: "2021-12-29 19:38:09 -0700"
tags: [Array, Two Pointers, Sorting]
level: Easy
---

# Problem

Given an integer array `nums` sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.
 

### Example 1:

Input: nums = [-4,-1,0,3,10]

Output: [0,1,9,16,100]

Explanation: After squaring, the array becomes [16,1,0,9,100].

After sorting, it becomes [0,1,9,16,100].

### Example 2:

Input: nums = [-7,-3,2,3,11]

Output: [4,9,9,49,121]
 
### Constraints:

- 1 <= nums.length <= 10^4
- -10^4 <= nums[i] <= 10^4
- nums is sorted in non-decreasing order.

# Solution - Two Pointers

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var sortedSquares = function(nums) {
    let low = 0;
    let high = nums.length - 1;
    while (low <= high){

        if (low === high){
            nums[low] = Math.pow(nums[low],2);
            return nums.sort((a,b) => a-b);
        }
        else {
            nums[low] = Math.pow(nums[low],2);
            low++;
            nums[high] = Math.pow(nums[high],2);
            high--;
        }

    }
    
    return nums.sort((a,b) => a-b);
};
{% endhighlight %}

Runtime: 187 ms, faster than 12.29% of JavaScript online submissions for Squares of a Sorted Array.

Memory Usage: 46.1 MB, less than 21.90% of JavaScript online submissions for Squares of a Sorted Array.

# Solution - Simple Math with Loop

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @return {number[]}
 */


var sortedSquares = function(nums) {
    
    for (i=0; i<nums.length; i++){
        nums[i] = Math.pow(nums[i],2);
        console.log(nums);
    }
    
    return nums.sort((a,b) => a-b);
    
};
{% endhighlight %}

This will work with short array. Output Limit Exceeded.