---
layout: post
title:  Tree traversals(Post,Pre,In) Without Recursion
published: true
category: Algorithm
---
Source: http://algorithms.tutorialhorizon.com
```java
public void inorderIteration(Node root) {
		Stack<Node> s = new Stack<Node>();
		while (true) {
			// Go to the left extreme insert all the elements to stack
			while (root != null) {
				s.push(root);
				root = root.left;
			}
			// check if Stack is empty, if yes, exit from everywhere
			if (s.isEmpty()) {
				return;
			}
			// pop the element from the stack , print it and add the nodes at
			// the right to the Stack
			root =s.pop();
			System.out.print(root.data + " ");
			root = root.right;
		}
	}

public void preorderIteration(Node root) {
		Stack<Node> s1 = new Stack<Node>();
		Stack<Node> s2 = new Stack<Node>();
		// push the root node into first stack.
		s1.push(root);
		while (s1.isEmpty() == false) {
			// take out the root and insert into second stack.
			Node temp = s1.pop();
			s2.push(temp);
			// now we have the root, push the left and right child of root into
			// the first stack.
			if(temp.left!=null){
				s1.push(temp.left);
			}
			if(temp.right!=null){
				s1.push(temp.right);
			}
		}
		//once the all node are traversed, take out the nodes from second stack and print it.
		System.out.println("Preorder Traversal: ");
		while(s2.isEmpty()==false){
			System.out.print(s2.pop());
		}
	}
  // postorder revrse of pre. so use another stack to keep elements to print in reverse
public void preorderIteration(Node root) {
		Stack<Node> s1 = new Stack<Node>();
		Stack<Node> s2 = new Stack<Node>();
		// push the root node into first stack.
		s1.push(root);
		while (s1.isEmpty() == false) {
			// take out the root and insert into second stack.
			Node temp = s1.pop();
			s2.push(temp);
			// now we have the root, push the left and right child of root into
			// the first stack.
			if(temp.left!=null){
				s1.push(temp.left);
			}
			if(temp.right!=null){
				s1.push(temp.right);
			}
		}
		//once the all node are traversed, take out the nodes from second stack and print it.
		System.out.println("Preorder Traversal: ");
		while(s2.isEmpty()==false){
			System.out.print(s2.pop());
		}
	}

```
