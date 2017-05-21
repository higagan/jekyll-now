---
layout: post
title:  Shortcut to print array elements in JAVA
published: true
category: Algorithm
---
Many time we need to print all array values to check if values are printing correctly. Its useful while debugging.

``` java
import java.util.Arrays;  // import this to use Arrays object

public class printArray {
	public static void main(String args[]) {
		int n[] = { 1, 9, 8, 7 };
		System.out.println(Arrays.toString(n));
	}
}



```
