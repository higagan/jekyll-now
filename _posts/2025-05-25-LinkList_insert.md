---
layout: post
title:  All insert operations of linked list
published: true
category: Algorithm
---

This is start of linked list series posts and here, I am presenting to you all kinds of insert operations performed on linked list.


``` java

public class LinkList {

	public class Node {
		int data;
		Node next;

		public Node(int data) {
			this.data = data;
			this.next = null;
		}
	}

	Node head = null;;

	public void insertAtEnd(int data) {
		Node N = new Node(data);
		if (head == null) {
			System.out.println("Node is empty inserting at first");
			head = N;
			return;
		} else {
			Node current = head;
			while (current.next != null)
				current = current.next;
			current.next = N;
			return;
		}

	}

	public void insertAtBeginning(int data) {
		Node N = new Node(data);
		if (head == null) {
			System.out.println("Node is empty inserting at first");
			head = N;
			return;
		} else {
			N.next = head;
			head = N;
			return;
		}

	}

	public void insertafterKthNode(int data, int key) {
		Node current = head;
		Node prev = head;
		Node N = new Node(data);
		for (int i = 1; i < key; i++) {
			prev = prev.next;
			current = current.next.next;
		}
		prev.next = N;
		N.next = current;
		return;

	}

	public void display() {
		Node current = head;
		while (current != null) {
			System.out.println(current.data);
			current = current.next;
		}
	}

	public static void main(String args[]) {
		LinkList L = new LinkList();
		L.insertAtEnd(6);
		L.insertAtEnd(12);
		L.insertAtEnd(13);
		L.insertAtBeginning(77);
		L.insertAtBeginning(779);
		L.insertafterKthNode(4, 2); // 4 is number to be inserted after 2nd place
		L.display();

	}

}

```
