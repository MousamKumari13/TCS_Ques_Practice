# Rank Transformation of an Array.

Problem Statement: Given an array of N integers, the task is to replace each element of the array by its rank in the array.

Examples:

Example 1:
# Input: 
```20 15 26 2 98 6```
# Output:
```4 3 5 1 6 2```

Explanation: When sorted,the array is 2,6,15,20,26,98. So the rank of 2 is 1,rank of 6 is 2,rank of 15 is 3 and so…

Example 2:
# Input: 
```1 5 8 15 8 25 9```
# Output: 
```1 2 3 5 3 6 4```

Explanation: When sorted,the array is 1,5,8,8,9,15,25. So the rank of 1 is 1,rank of 5 is 2,rank of 8 is 3 and so…*/
# Problem Link ->
https://leetcode.com/problems/rank-transform-of-an-array/description/

# Solution 
```C++
#include<bits/stdc++.h>
using namespace std;
vector<int> SortByRank(vector<int> & arr , int n){
    if(n == 0) return {};
    
    set<int> s(arr.begin() , arr.end());
    
    unordered_map<int , int> mpp;
    int rank = 1;
    
    for(auto it = s.begin(); it != s.end() ; it++){
        mpp[*it] = rank;
        rank++;
    }
    
    for(int i =0 ;i< n ;i++){
        arr[i] = mpp[arr[i]];
    }
    return arr;
}
int main() {
    int n;
    cin>>n ;
    vector<int> arr(n);
    
    for(int i =0 ;i < n ;i++){
        cin>>arr[i];
    }
    SortByRank(arr , n);
    for(int i =0 ;i< n ;i++){
        cout<<arr[i]<<" ";
    }
   return 0;
}
```
# video Link -> https://youtu.be/f1nZp5Mr3XE?si=rXP2RsJuYy4cMYtd

# Complexity

Time Complexity:
Overall: O(n⋅logn)
Sorting via set insertion: O(n⋅logn)
Mapping and updating ranks: O(n)

Space Complexity:
Overall: O(n)
set<int> and unordered_map<int, int> store up to n unique elements.
