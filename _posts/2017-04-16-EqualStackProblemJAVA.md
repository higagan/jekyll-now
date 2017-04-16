---
published: false
---
## A New Post
---
published: true
---
## A New Post
---
layout: post
title: Print binary numbers
published: true
---
Problem:
You have three stacks of cylinders where each cylinder has the same diameter, but they may vary in height. You can change the height of a stack by removing and discarding its topmost cylinder any number of times.

Find the maximum possible height of the stacks such that all of the stacks are exactly the same height. This means you must remove zero or more cylinders from the top of zero or more of the three stacks until they're all the same height, then print the height. The removals must be performed in such a way as to maximize the height.
Here is JAVA implemnetation of it:
``` java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
import java.util.stream.*;

public class Solution {
    public static int getMinValue(int[] array) {
            int minValue = array[0];
            for (int i = 1; i < array.length; i++) {
            if (array[i] < minValue) {
            minValue = array[i];
            }
        }
               
        return minValue;
        }
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n1 = in.nextInt();
        int n2 = in.nextInt();
        int n3 = in.nextInt();
        int h1[] = new int[n1];
        for(int h1_i=0; h1_i < n1; h1_i++){
            h1[h1_i] = in.nextInt();
        }
        int h2[] = new int[n2];
        for(int h2_i=0; h2_i < n2; h2_i++){
            h2[h2_i] = in.nextInt();
        }
        int h3[] = new int[n3];
        for(int h3_i=0; h3_i < n3; h3_i++){
            h3[h3_i] = in.nextInt();
        }
        int h1_size= IntStream.of(h1).sum();
        int h2_size= IntStream.of(h2).sum();
        int h3_size= IntStream.of(h3).sum();
        int h1_i=0;
        int h2_i=0;
        int h3_i=0;
       
        while(true){
        if(h1_size>h2_size && h1_size>h3_size)
            h1_size -= h1[h1_i++];
        else if (h2_size>h1_size && h2_size>h3_size)    
            h2_size -= h2[h2_i++];
        else if (h3_size>h1_size && h3_size>h2_size)    
            h3_size -= h3[h3_i++];
        else
            break;
        }
       
        System.out.print(h1_size);
       
       
    }
}
```