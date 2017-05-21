---
layout: post
title:  Print pattern using recursion
published: true
category: Algorithm
---
print below pattern using recursion:
16 11 6 1 -4 1 6 11 16 
16 shloud get decremented by 5 and when it reaches negative value it should start increasing. The program should terminate when 16 repeats again.

``` java 

public class Pattern {

	public static void pattern(int n, boolean flag, int p) {

		if (n > 16 && flag == true)
			return;

		System.out.println(n + " ");

		if (n < 0) {
			p = Math.abs(p);
			flag = true;
		}
		pattern(n + p, flag, p);

	}

	public static void main(String args[]) {
		int n = 16, p = -5;
		boolean flag = false;
		pattern(n, flag, p);
	}

}



```
