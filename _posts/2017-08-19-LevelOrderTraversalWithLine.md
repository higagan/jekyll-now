---
layout: post
title:  Level order traversal line by line
published: true
category: Algorithm
---

``` java
static void printLevelOrder(Node root){
	   if(root==null)
		   return;
	   Queue<Node> q = new LinkedList<Node>();
	   q.add(root);
	   
	   while(true){
		   int nodeCount = q.size();
		   if(nodeCount == 0)
			   break;
		   while(nodeCount > 0){               //after loop terminates , change line
			   Node myNode = q.peek();
			   System.out.print(myNode.data+" ");
			   q.remove();
			   if(myNode.right!=null)
				   q.add(myNode.right);
			   if(myNode.left!=null)
				   q.add(myNode.left);
			   nodeCount--;
		   }
		   System.out.println();  // to chnage line
	   }
   }

```
