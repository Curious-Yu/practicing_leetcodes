---
layout: post
title: "Binary Search Notes"
date: "2021-12-28 13:38:09 -0700"
tags: [Binary Search]
level: Note
---

# What is Binary Search?

A binary search is an advanced type of search algorithm that finds and fetches data from a sorted list of items. Its core working principle involves dividing the data in the list to half until the required value is located and displayed to the user in the search result. Binary search is commonly known as a half-interval search or a logarithmic search.

# How Binary Search Works?

The binary search works in the following manner:

- The search process initiates by locating the middle element of the sorted array of data
- After that, the key value is compared with the element
- If the key value is smaller than the middle element, then searches analyses the upper values to the middle element for comparison and matching
- In case the key value is greater than the middle element then searches analyses the lower values to the middle element for comparison and matching

# Example

![binary search example](/pic/binarysearch1.png)

A. You have an array of sorted values ranging from 2 to 20 and need to locate 18.

B. The average of the lower and upper limits is (l + r) / 2 = 4. The value being searched is greater than the mid which is 4.

C. The array values less than the mid are dropped from search and values greater than the mid-value 4 are searched.

D. This is a recurrent dividing process until the actual item to be searched is found.

# More info

[<i class="far fa-hand-pointer"></i> Binary Search Algorithm with EXAMPLE - Guru99](https://www.guru99.com/binary-search.html)

[<i class="far fa-hand-pointer"></i> Binary search - Khan Academy](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search)