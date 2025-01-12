# find the maximum number in every contiguous subarray of size k.
Given an array of integers, find the maximum number in every contiguous subarray of size k.
Input:
The first line contains an array of integers separated by spaces.
The second line contains an integer  k, the size of the subarray.
Output:
Print the maximum number for each contiguous subarray of size 
k, separated by spaces.
## Constraints:
size of array  1≤k≤size of array elements 1 ≤ array elements ≤ 10^5
 
Example:
## Input:
```1 3 -1 -3 5 3 6 7```
```3```
## Output:
```3 3 5 5 6 7```
Explanation:
For k=3:

The first subarray is [1,3,−1]: Max = 3
The second subarray is [3,−1,−3]: Max = 3
The third subarray is [−1,−3,5]: Max = 5
The fourth subarray is [−3,5,3]: Max = 5
The fifth subarray is [5,3,6]: Max = 6
The sixth subarray is [3,6,7]: Max = 7

## Problem Link -> 
https://www.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=longest-sub-array-with-sum-k

# Solution([Postives and Negatives Array Elements])
```C++
#include <bits/stdc++.h>
using namespace std;
int longestSubarrayWithSumK(vector<int>& a, int k) {
    map<int, int> mp;
    int sum =0;
    int maxlength =0;
    
    for(int i =0 ;i< a.size() ; i++){
        sum += a[i];
        if(sum == k){
            maxlength = max(maxlength , i+1);
        }
        
        int rem = sum - k;
        if(mp.find(rem) != mp.end()){
            int len = i - mp[rem];
            maxlength = max(maxlength , len);
        }
        
        if(mp.find(sum) == mp.end()){
            mp[sum] = i;
        }
    }
   return maxlength;
}
int main()
{
   int n;
    cin>>n;
    vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    int target;
    cin>>target;
    cout<<longestSubarrayWithSumK(arr , target );
    return 0;
}
```
# Complexity 

Time Complexity: ```O(N) or O(N*logN)``` depending on which map data structure we are using, where N = size of the array.

Reason: For example, if we are using an unordered_map data structure in C++ the time complexity will be O(N)(though in the worst case, unordered_map takes O(N) to find an element and the time complexity becomes O(N2)) but if we are using a map data structure, the time complexity will be O(N*logN). The least complexity will be O(N) as we are using a loop to traverse the array.

Space Complexity: ```O(N)``` as we are using a map data structure.

# Solution(Array containing element as (0 or positive)) 2 pointer Optimal Approach
```C++

#include <bits/stdc++.h>
using namespace std;

int longestSubarrayWithSumK(vector<int> a, long long k) {
  int left = 0 , right =0 ;
  long long sum = a[0];
  int maxLength = 0;
  int n = a.size();
  while(right < n){
     while(left <= right && sum > k){
         sum -= a[left];
         left++;
     }
     if(sum == k){
         maxLength= max(maxLength , right - left+1);
     }
     right ++;
     if(right < n) sum += a[right];
  }
   return maxLength;
}

int main()
{
    int n;
    cin>>n;
    vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    int target;
    cin>>target;
    cout<<longestSubarrayWithSumK(arr , target );
    return 0;
}
```
# Complexity Analysis

Time Complexity: ```O(2*N)```, where N = size of the given array.

Reason: The outer while loop i.e. the right pointer can move up to index n-1(the last index). Now, the inner while loop i.e. the left pointer can move up to the right pointer at most. So, every time the inner loop does not run for n times rather it can run for n times in total. So, the time complexity will be O(2*N) instead of O(N2).

Space Complexity: ``` O(1) ```as we are not using any extra space.