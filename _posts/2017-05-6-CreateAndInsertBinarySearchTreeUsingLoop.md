---
layout: post
title:  Create and Insert elemnets Without Recursion in Binary Search Tree
published: true
category: Algorithm,Data Structure
---
Here, we will learn to insert elemnts in BST using loop.

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
	}
	// function using loop to insert a new key in BST
	public void insert(int data) {
		// create new node 
		TreeNode newNode = new TreeNode(data);
		// If the tree is empty, return a new node by assigning newNode to root
		if (root == null)
			root = newNode;
		else {
			// current node to iterate and parent node to insert value
			TreeNode current = root;
			TreeNode parent; // this is to hold the immediate parent root of the new element
			while (true) {
				parent = current; 
				// if new data is less than root data, move left
				if (current.data > data) {
					current = current.left;
					if (current == null) {
						parent.left = newNode; // Now current is null. So, use immediate parent to insert new node to this location 
						return;
					}
				} else {
					// if new data is more than root data, move right
					current = current.right;
					if (current == null) {
						parent.right = newNode; // Now current is null. So, use immediate parent to insert new node to this location 
						return;
					}
				}
			}

		}

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
