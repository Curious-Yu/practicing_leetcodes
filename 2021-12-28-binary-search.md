---
layout: post
title: "Binary Search"
date: "2021-12-28 19:38:09 -0700"
tags: [Array, Binary Search]
level: Easy
---

# Problem

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search target in `nums`. If target exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

### Example 1:

Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4

### Example 2:

Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
 

### Constraints:

- 1 <= nums.length <= 10^4
- -10^4 < nums[i], target < 10^4
- All the integers in nums are unique.
- nums is sorted in ascending order.

# Solution - Binary Search

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    let low = 0;
    let high = nums.length-1;
    let mid;
    console.log(mid);
    
    while (low <= high){
        mid = Math.floor((low+high)/2);
        console.log(low, mid, high);
        if (nums[mid] === target){
            return mid;
        }
        else if (nums[mid] < target){
            low = mid+1;
        }
        else {
            high = mid-1;
        }
    }
    
    return -1;

};
{% endhighlight %}

Runtime: 88 ms, faster than 21.08% of JavaScript online submissions for Binary Search.

Memory Usage: 42.9 MB, less than 5.62% of JavaScript online submissions for Binary Search.

# Solution - Array

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    let i = 0;
    for (i=0; i < nums.length; i++){
        if (nums[i] === target){
            return i;
        }
    }
    
    return -1;

};
{% endhighlight %}

Runtime: 76 ms, faster than 79.00% of JavaScript online submissions for Binary Search.

Memory Usage: 42.6 MB, less than 24.50% of JavaScript online submissions for Binary Search.


# Note

algorithm with O(log n) runtime complexity

![big-O complexity chart](/pic/big-O-chart.png)