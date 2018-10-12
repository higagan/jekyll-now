---
layout: post
title:  Balanced Brackets
published: true
category: Algorithm
---

Balanced brackets is one of the popular problem. 
Read about the problem here: https://www.hackerrank.com/challenges/balanced-brackets

One of the best ways is to solve it using Stacks. Below is my solution using C++ STL:

``` c++
#include <stack>
#include <iostream>

using namespace std;

bool arePairs(char opening,char closing){
    if( opening == '(' && closing == ')' ) return true;
    else if( opening == '{' && closing == '}' ) return true;
    else if( opening == '[' && closing == ']' ) return true;
    return false;
    
}

bool isBalanced(string s){
    stack<char> st;int i;
    bool ans = true;
    for (i=0;i<s.length();i++){
        if(s[i]=='(' || s[i]=='{' || s[i]=='[')
        st.push(s[i]);
        if(s[i]==')' || s[i]=='}' || s[i]==']'){
            if(st.empty() || !arePairs(st.top(),s[i]))
               return false;
            else{
                st.pop();
                ans=true;
        }
    }
    
}
  return st.empty() ? true:false;  
}

int main(){
    int t;
    cin >> t;
    for(int a0 = 0; a0 < t; a0++){
        string s;
        cin >> s;
    if(isBalanced(s))
        cout << "YES\n";
    else
        cout << "NO\n";
    }
    
    return 0;
}


```
