# Algorithms-and-Data-Structures
This repository consists of the code samples, assignments and data structure problems.
### <h1 align="center"> LeetCode Problem</h1>
### <ol>Problem Statement: <a href="https://leetcode.com/problems/assign-cookies/submissions/1438926506">**Given two arrays representing children’s green factor and cookie sizes, the goal is to maximise the number of content children.**</a></ol>
```c++
Each child i has a greed factor of g[i], which is the minimum size of a cookie that will make the child content. Each cookie j has a size of s[j]. If s[j] >= g[j], we can assign cookie j to child i, making the child content. Each child can only receive one cookie.
```
### <ol>Problem Statement: <a href="https://leetcode.com/problems/lemonade-change/submissions/1439944608">** Given an array representing a queue of customers and the value of bills they hold, determine if it is possible to provide correct change to each customer. Customers can only pay with 5$, 10$ or 20$ bills and we initially do not have any change at hand. Return true, if it is possible to provide correct change for each customer otherwise return false.**</a></ol>
```c++
Example 1:

Input: bills = [5,5,5,10,20]
Output: true
Explanation: 
From the first 3 customers, we collect three $5 bills in order.
From the fourth customer, we collect a $10 bill and give back a $5.
From the fifth customer, we give a $10 bill and a $5 bill.
Since all customers got correct change, we output true.
Example 2:

Input: bills = [5,5,10,10,20]
Output: false
Explanation: 
From the first two customers in order, we collect two $5 bills.
For the next two customers in order, we collect a $10 bill and give back a $5 bill.
For the last customer, we can not give the change of $15 back because we only have two $10 bills.
Since not every customer received the correct change, the answer is false.
 
```

### <ol>Problem Statement: Shortest Job first- **</a></ol>

```c++
Example 1:

Input:
n = 5
bt = [4,3,7,1,2]
Output: 4
Explanation: After sorting burst times by shortest job policy, calculated average waiting time is 4.
 
```
// User function Template for C++

// Back-end compolete function Template for C++

class Solution {
  public:
    long long solve(vector<int>& bt) {
        sort(bt.begin(),bt.end());
        float wait_time=0;
        int total_time=0;
        int n=bt.size();
        for(int i=0;i<n;i++){
            wait_time+=total_time;
            total_time+=bt[i];
        }
        return wait_time/n;
    }
};

### <h1 align="center"> LeetCode Problem</h1>
### <ol>Problem Statement: Jump Game <a href="https://leetcode.com/problems/jump-game/submissions/1441794463">**You are given an integer array nums. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.
Return true if you can reach the last index, or false otherwise. **</a></ol>
```c++
Example 1:

Input: nums = [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
Example 2:

Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```

### <h1 align="center"> Binary Tree implementation</h1>
```
// Binary Tree implementation using C++

#include<iostream>
#include<string>
using namespace std;
class BinaryTree{
    private:
    struct Node{
        int value;
        Node* left;
        Node* right;
        Node(int val):value(val),left(nullptr),right(nullptr){}
    };
    Node* root;
    public:
    BinaryTree():root(nullptr){}
    void insert(){
        int value;
        cout<<"Enter root to insert: ";
        cin>>value;
        root =new Node(value);
        insert(root);
    }
    void insert(Node* node){
        char response;
        cout <<"do you want to insert left node "<<node->value<<"(y/n): ";  
        cin>>response;
        if(response=='y'||response=='Y'){
            int value;
            cout<<"Enter left node to insert:";
            cin>>value;
            node->left=new Node(value);
            insert(node->left);
        }
    
        cout <<"do you want to insert right node "<<node->value<<"(y/n): ";  
        cin>>response;
        if(response=='y'||response=='Y'){
            int value;
            cout<<"Enter right node to insert:";
            cin>>value;
            node->right=new Node(value);
            insert(node->right);
        }
    }
    void display(Node* node,string indent){
        if(node==nullptr){
            return;
        }
        cout<<indent<<node->value<<endl;
        display(node->left,indent+"\t");
        display(node->right,indent+"\t");
    }
    void display(){
        display(root,"");
    }
};
int main(){
BinaryTree tree;
tree.insert();
tree.display();
return 0;
}
