---
layout: post
title: "Middle of the Linked List"
date: "2022-01-01 20:59:03 -0700"
tags: [Two Pointers, Linked List]
level: Easy
---

# Problem

Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.

 

### Example 1:


Input: head = [1,2,3,4,5]

Output: [3,4,5]

Explanation: The middle node of the list is node 3.

### Example 2:


Input: head = [1,2,3,4,5,6]

Output: [4,5,6]

Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.
 

### Constraints:

The number of nodes in the list is in the range [1, 100].

1 <= Node.val <= 100

# Solution 

{% highlight js %}
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var middleNode = function(head) {
    
    let i = head;
    let j = head;
    
    let count = 0;
    
    while(i){
        i = i.next;
        count++;
    }
    
    let half = Math.floor(count/2);
    
    while(j){
        if(half === 0){
            return j;
        };
        j=j.next;
        half--;
    }
};
{% endhighlight %}

Runtime: 72 ms, faster than 69.57% of JavaScript online submissions for Middle of the Linked List.

Memory Usage: 38.4 MB, less than 95.26% of JavaScript online submissions for Middle of the Linked List.
