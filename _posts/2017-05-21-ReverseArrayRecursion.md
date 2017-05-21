---
layout: post
title:  Reverse array elements using recursion
published: true
category: Algorithm, recursion
---
Reevrse all array elements using recursion. JAVA implementation

```java
import java.util.Arrays;

public class reverseArray {
	public static void reverse(int n[], int i, int j) {
		if (i < j) {
			int tempi, tempj;
			tempi = n[i];
			tempj = n[j];
			n[i] = tempj;
			n[j] = tempi;
			reverse(n, i = i + 1, j = j - 1);
		}
	}

	public static void main(String args[]) {
		int n[] = { 1, 9, 8, 7 };
		int i = 0, j = n.length - 1;
		reverse(n, i, j);
		System.out.println(Arrays.toString(n)); // java inbuilt to print array
	}

}

```
