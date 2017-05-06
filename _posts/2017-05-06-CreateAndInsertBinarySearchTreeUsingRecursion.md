---
layout: post
title: Create Binary Search Tree and Insert elements using Recursion
published: true
category: Algorithm
---
Here, we will learn to insert elements in BST using recursion. 


```java
public class MyTree {
	// class to create current node with its value
	class TreeNode {
		int data;
		TreeNode left;
		TreeNode right;

		public TreeNode(int data) {

			this.data = data;
			this.left = null;
			this.right = null;

		}
	}
	// Root of BST
	TreeNode root;
	// use Constructor to initialize root to null while creating BST
	MyTree() {
		root = null;
	}	// function to call recursive function
	public void insert(int data) {
		
		root=insert(root,data);
	}
	// function using recursion to insert a new key in BST
	private TreeNode insert(TreeNode root,int data){
		if(root==null){ // If the tree is empty, return a new node by assigning newNode to root
			TreeNode newNode = new TreeNode(data);
			root=newNode;
			return root;
		}
		else{
			if(root.data>data){ // if new data is less than root data, insert to left of tree
				root.left = insert(root.left,data);
			}else
				root.right = insert(root.right,data); // if new data is greater than root data, insert to right of tree
			}
		return root;
	}
	public void inorder() {
		inorder(root);
	}

	private void inorder(TreeNode root2) {
		if (root2 != null) {
			inorder(root2.left);
			System.out.println(root2.data);

			inorder(root2.right);
		}
		// TODO Auto-generated method stub

	}

	public static void main(String args[]) {

		MyTree tree = new MyTree();
		tree.insert(6);
		tree.insert(45);
		tree.insert(2);
		tree.insert(20);
		tree.insert(50);
		tree.inorder(); 

	}

}
```
