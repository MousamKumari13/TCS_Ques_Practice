# Find Elements Appearing More Than N/3 Times .

Write a program to find all the elements in an array that appear more than ⌊N/3⌋ times, where N is the size of the array.

Given:
An integer array arr of size N.
Input:

An array of integers arr.
The size of the array N.
Output: Print all the elements that appear more than ⌊N/3⌋ times in the array. If no such element exists, print nothing.
Constraints:
The array can contain positive, negative, and zero values.
The solution should efficiently count the frequencies of elements.
Example 1:
## Input:
```arr = [3, 2, 3, 2, 2, 1, 3]```
```N = 7```
## Output: 2  3

# solution
```C++
#include <bits/stdc++.h>
using namespace std;
void maxele(vector<int>& arr){
    unordered_map<int,int> mp;
    for(int ele : arr){
        mp[ele]++;
    }
    vector<int> ans;
    int n = arr.size();
    for(auto num : mp){
        if(num.second >= n/3){
            ans.push_back(num.first);
        }
    }
    for(int i=0 ;i<ans.size();i++){
        cout<<ans[i]<<" ";
    }
}
int main()
{
     int n;
     cin>>n;
     
     vector<int> arr(n);
     for(int i =0 ;i<n ;i++){
         cin>>arr[i];
     }
     
     maxele(arr);
    return 0;
}
```
## Complexity
Time Complexity: O(n)
Space Complexity: O(n)