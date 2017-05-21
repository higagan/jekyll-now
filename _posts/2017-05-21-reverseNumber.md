---
layout: post
title: Reverse number using Recursion
published: true
category: Algorithm, Recursion
---

``` java
Reverse any number using recursion. 
JAVA implementation:

public class reverseNumber {
	public static int reverse(int n, int rev) {
		rev = rev * 10;
		rev = rev + (n % 10);
		if (n > 10) {
			rev = reverse(n / 10, rev);
		}
		return rev;
	}

	public static void main(String args[]) {
		int n = 7641;
		int rev = reverse(n, 0);
		System.out.println(rev);
	}
}

```
