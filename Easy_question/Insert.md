# Problem Statement: Given an array of N integers, write a program to add an array element at the beginning, end, and at a specific position.

Example:
# Input:
``` N = 5, array[] = {1,2,3,4,5}```
insertbeginning(6)
insertending(7)
insertatpos(8,4)
# Output: 
```6,1,2,8,3,4,5,7```
Explanation: 6 is added at the beginning and 7 is added at the end and 8 is added at position 4

# Solution
```C++

#include <bits/stdc++.h>
using namespace std;
void insertAtBegining(vector<int>& arr , int value){
    arr.insert(arr.begin(), value);
}

void insertAtEnd(vector<int>& arr , int value){
    arr.push_back(value);
}
void insertAtPOs(vector<int>& arr , int value, int pos){
    arr.insert(arr.begin() + pos-1 ,value);
}
int main() {
   int n ;
   cin>>n ;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
  int value;
  cin>>value;
  insertAtBegining(arr ,value);
  int ele ;
  cin>>ele;
  insertAtEnd(arr, ele);
  int element, pos;
  cin>>element>>pos;
  insertAtPOs(arr ,element , pos);
  
  for(int i =0 ;i < arr.size() ;i++){
      cout<<arr[i]<<",";
  }
  cout<<endl;
    return 0;
}
```
