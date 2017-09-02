---
layout: post
title:  Height of Tree
published: true
category: Algorithm
---

``` java
static int height(Node root) {
      	// Write your code here.
        if(root==null)
            return 0;
        int l=0,h=0;
        if (root.left != null)
            l=1+height(root.left);
        if (root.right != null)
            h=1+height(root.right);
        if(l>h)
            return l;
        else
            return h;
    }


```
