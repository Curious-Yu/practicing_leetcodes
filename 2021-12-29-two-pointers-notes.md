---
layout: post
title: "Two Pointers Notes"
date: "2021-12-29 13:38:09 -0700"
tags: [Two Pointers]
level: Note
---

# What is two pointers?

This approach optimizes the runtime by utilizing some order (not necessarily sorting) of the data. It is generally applied on lists (arrays) and linked lists. This is generally used to search pairs in a sorted array. This approach works in constant space.

In this technique pointers represent either index or an iteration attribute like node’s next.

# Example

![two pointers example](/pic/two-pointers.png)

### Pointer Initialization — Starting points. 

Pointers can be at any place depending upon what we are trying to achieve. In the left part of the pic, we have both pointers starting at the same position i.e. start of the linked list. In the right part of the pic, we have pointers at extreme ends one at starting index and another one at the last index.

### Pointer movement — This will decide how we converge towards the solution.

Pointer can move in the same direction (left in above pic) or they can move in the opposite direction (right in the above pic). Also in the left part of the pic, we have different increments for the pointers(top (slow) with 1 unit bottom (fast) with 2 units).

### Stop condition — This decides when do we stop. 

In the left part, we continue till we reach a node whose next element is None. In the right one, we continue till our start is less than the end (i < j).

# More Info

[<i class="far fa-hand-pointer"></i> Two Pointer Approach](https://towardsdatascience.com/two-pointer-approach-python-code-f3986b602640)

[<i class="far fa-hand-pointer"></i> Using the Two Pointer Technique](https://algodaily.com/lessons/using-the-two-pointer-technique)

