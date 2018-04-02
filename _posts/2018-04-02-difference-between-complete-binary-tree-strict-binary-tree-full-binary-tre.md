---
layout: post
title:  Difference between Complete binary tree, strict binary tree and full binary Tree
published: true
category: Data Structure
---

 Here is a difference between a STRICT and FULL BINARY TREE.

1) FULL BINARY TREE: A binary tree of height h that contains exactly (2^h)-1 elements is called a full binary tree. (Ref: Pg 427, Data Structures, Algorithms and Applications in C++ [University Press], Second Edition by Sartaj Sahni).

or in other words

In a FULL BINARY TREE each node has exactly 0 or 2 children and all leaf nodes are on the same level.

For Example: The following is a FULL BINARY TREE:

          18
       /      \   
     15       30    
    /  \     /   \   
  40    50  100  40 
2) STRICT BINARY TREE: Each node has exactly 0 or 2 children.

For example: The following is a STRICT BINARY TREE:

         18
       /     \   
     15       30    
    /  \          
  40    50
I think there's no confusion in the definition of a Complete Binary Tree, still for the completeness of the post I would like to tell what a Complete Binary Tree is.

3) COMPLETE BINARY TREE: A Binary Tree is complete Binary Tree if all levels are completely filled except possibly the last level and the last level has all keys as left as possible.

For Example: The following is a COMPLETE BINARY TREE:

           18
       /       \  
     15         30  
    /  \        /  \
  40    50    100   40
 /  \   /
8   7  9 
Note: The following is also a Complete Binary Tree:

         18
       /     \   
     15       30    
    /  \     /   \   
  40    50  100  40 

Source: https://stackoverflow.com/questions/12359660/difference-between-complete-binary-tree-strict-binary-tree-full-binary-tre
