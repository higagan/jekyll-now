---
layout: post
title:  Shortcut in JAVA to find number of occurence all elements in array 
published: true
category: Algorithm
---

This can be achieved using for-each implementation in JAVA.

``` java
   numbers[10] = {10,20,10,20,50,50,91,80,90,91};
   int count[] = new int[100];
   for (int a : numbers) {
        	count[a]++;
        }

```
Count will give each element's count value.
