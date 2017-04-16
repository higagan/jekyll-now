---
layout: post
title: Print binary numbers
published: true
---
This is an interesting way to print binary numbers 
```java
import java.util.*;

public class Binary {
    public static void main(String[] args) throws InterruptedException {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        Queue<String> queue = new LinkedList<String>();
        String s1,s2;
        queue.add("1");

        while(n>0){
         s1=queue.remove();
         System.out.println(s1);
         s2=s1;
   queue.add(s1.concat("0"));
          queue.add(s2.concat("1"));
          n--;
        }
     }
}
  ```
