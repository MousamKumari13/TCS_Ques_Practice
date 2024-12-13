# Find the smallest Element
Problem Statement: Given an array, we have to find the smallest element in the array.

Examples:

Example 1:
# Input:
``` arr[] = {2,5,1,3,0};```
Output: 0
Explanation: 0 is the smallest element in the array. 

Example2: 
# Input: 
```arr[] = {8,10,5,7,9};```
Output: 5
Explanation: 5 is the smallest element in the array.

# Solution

```C++

#include <bits/stdc++.h>
using namespace std;
int findsmallestelement(int n, vector<int>& arr){
    int min_ele = INT_MAX;
    for(int i =0 ; i< n ;i++){
        if(arr[i] < min_ele){
            min_ele = arr[i];
        }
    }
    return min_ele;
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   cout<<findsmallestelement(n,arr)<<endl;
    return 0;
}

```