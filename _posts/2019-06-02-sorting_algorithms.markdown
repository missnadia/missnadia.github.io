---
layout: post
title:      "sorting algorithms"
date:       2019-06-02 20:05:01 -0400
permalink:  sorting_algorithms
---

researching popular sorting algorithms.


**Bubble Sort**<br>
![](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)
* inefficient for large lists
* compares first two elements. if the first is greater than the second, it swaps them. repeats until the list is passed through without any swaps.

**Insertion Sort**<br>
![](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)
* inefficient for large lists
* takes elements from list one by one and inserts them into their correct position in a new sorted list

**Selection Sort**<br>
![](https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif)
* inefficient for large lists
* performs worse than insert sort
* finds minimum value, swaps with value in first position. repeats for remaining elements on list.

**Merge Sort**<br>
![](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)
* divides unsorted list into sublists containing one element. then merges the sublists to produce new sorted sublsits until 1 sublist containing the sorted list remains.

**HeapSort**<br>
![](https://upload.wikimedia.org/wikipedia/commons/1/1b/Sorting_heapsort_anim.gif)
* more efficient selection sort
* determines smallest/largest element of the unsorted list, placing it at the beginning/end of the sorted list
* minimum/maximum element is determined by the use of a heap data structure instead of a linear-time search

**QuickSort** (partition-exchange sort)<br>
![](https://upload.wikimedia.org/wikipedia/commons/6/6a/Sorting_quicksort_anim.gif)
* faster than merge sort and heapsort
* divide and conquer algorithm -- breaks down a problem into two or more smaller problems of the same or related type until it can be solved
* selects element x in array as pivot, putting elements smaller/less than x before x, and elements greater than x after x.

