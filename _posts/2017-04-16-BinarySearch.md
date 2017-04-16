
---
layout: post
title: Print binary numbers
published: true
---

Given a sorted array , we need to find a element in this array. One way is to do linear search i.e 
compare each element with the number to be found. But this takes lots of time and complexity is O(n).
A better approach is by using Binary search. Here, we basically do these steps:
1. Compare the number to be found(x) with mid of the array, if found return its index
2. but if x is greater than middle element, this means that element is on the right side of mid element
   so, we restrict our search to this side only with recurrence.
3. similarly , if x is less than mid element , we search only left side.
So, we can understand that each time we are eliminating half of our elements from being compared. Hence , performance
gets improved and time complexity is only O(logn).

``` c++
#include<iostream>
using namespace std;
int binarySearch(int *arr,int low,int high,int toFind){
 int mid;
 if(low<=high){       // if this condition fails, this means number are looking is not present 
  mid=(low+high)/2;
  if(arr[mid]==toFind)   //  number found 
   return mid;
  if(toFind>arr[mid]){   // element lies to the right side 
   low=mid+1;            // starting point now changes accordingly to handle right side range
   binarySearch(arr,low,high,toFind);
  }
  if(toFind<arr[mid]){
   high=mid-1;             // last point now changes accordingly to handle left side range
   binarySearch(arr,low,high,toFind);
  }
 }
 else
  return -1;               // return -1 if number not found
}

int main(){

 int n,toFind,position,low=0,i;
 cout << "Enter size of array:";
 cin >> n;
 int arr[n];
 cout << "Enter the elements of the array:";
 
 for(i=0;i<n;i++){
  cin >> arr[i];
 }
 cout << "Enter the number to be search:";
 cin >> toFind;
 
 int high=n-1;
 // if element lies on any boundary of array , then no need to call Binary search function 
 if(toFind==arr[low])
  cout << "Number found at " << low << " index of array";
 else if(toFind==arr[high])
  cout << "Number found at " << high << " index of array"; 
 else
  position=binarySearch(arr,low,high,toFind);
 if(position == -1)
  cout << "Number not found";
 else
  cout << "Number found at " << position ";
 }
 return 0;
}
```
