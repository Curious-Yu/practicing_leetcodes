---
layout: post
title: "Rotate Array"
date: "2021-12-29 20:38:09 -0700"
tags: [Two Pointers, Math, Array]
level: Medium
---

# Problem

Given an array, rotate the array to the right by k steps, where k is non-negative.

### Example 1:

Input: nums = [1,2,3,4,5,6,7], k = 3

Output: [5,6,7,1,2,3,4]

Explanation:

rotate 1 steps to the right: [7,1,2,3,4,5,6]

rotate 2 steps to the right: [6,7,1,2,3,4,5]

rotate 3 steps to the right: [5,6,7,1,2,3,4]

### Example 2:

Input: nums = [-1,-100,3,99], k = 2

Output: [3,99,-1,-100]

Explanation: 

rotate 1 steps to the right: [99,-1,-100,3]

rotate 2 steps to the right: [3,99,-1,-100]
 

### Constraints:

1 <= nums.length <= 10^5
-2^31 <= nums[i] <= 2^31 - 1
0 <= k <= 10^5
 

### Follow up:

Try to come up with as many solutions as you can. There are at least three different ways to solve this problem.

Could you do it in-place with O(1) extra space?

# Solution - failed b/c Time Limit Exceeded

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
    
    let last = nums.length -1
    
    while(k > 0){
        nums.unshift(nums[last]);
        nums.pop(nums[last]);
        k--;
    }
    return nums;
};
{% endhighlight %}

# Solution

{% highlight JavaScript %}
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
    
    let moveNums = k%nums.length;
    let stayNums = nums.length - moveNums;
    
    console.log(moveNums)
    
    for (i=0; i < stayNums; i++){
        nums.push(nums[i]);
    }
    
    return nums.splice(0,stayNums);
    
    console.log(nums)

};
{% endhighlight %}

Runtime: 204 ms, faster than 5.08% of JavaScript online submissions for Rotate Array.

Memory Usage: 49.8 MB, less than 21.95% of JavaScript online submissions for Rotate Array.

# Note

Using `%` modulo is the key!