---
layout: post
title: Find an element and Find root in BST
published: true
category: Algorithm
---

``` java
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
	
	public void Find(int data){
		root=Find(root,data);
		
	}
	private TreeNode Find(TreeNode root,int data){
		if (root == null) {
			System.out.println(data+" NOT FOUND");
	        return root;
	    }
		if(root.data==data){
			System.out.println(data+" FOUND");
			return root;
		}
		else
		{
			if(root.data>data)
				root.left=Find(root.left,data);
			else
				root.right=Find(root.right,data);
			
		}
	
		return root;
	}
	public void findRoot(){
		System.out.println("Root element is "+root.data);
	}
	public static void main(String args[]) {

		MyTree tree = new MyTree();
		tree.insert(6);
		tree.insert(45);
		tree.insert(2);
		tree.insert(20);
		tree.insert(50);
		tree.Find(45);
    tree.Find(4);
		tree.findRoot();

	}

}
