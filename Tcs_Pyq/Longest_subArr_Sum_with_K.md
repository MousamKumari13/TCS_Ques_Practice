# Longest Subarray with given Sum K(Positives)

Problem Statement: Given an array and a sum k, we need to print the length of the longest subarray that sums to k.

Examples
Example 1:
## Input Format: 
```N = 3, k = 5, array[] = {2,3,5}```
## Result: 2

Explanation: The longest subarray with sum 5 is {2, 3}. And its length is 2.

Example 2:
## Input Format: 
```N = 5, k = 10, array[] = {2,3,5,1,9}```
## Result: 3

Explanation: The longest subarray with sum 10 is {2, 3, 5}. And its length is 3.

# Problem Link->
https://www.naukri.com/code360/problems/longest-subarray-with-sum-k_6682399?utm_source=youtube&utm_medium=affiliate&utm_campaign=striver_Arrayproblems&leftPanelTabValue=PROBLEM

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
int longestsubArr_with_Sum_K( vector<int>& arr , int target){
    map<int,int> presummp;
    int sum =0 ;
    int maxLength = 0;
    for(int i =0 ;i< arr.size(); i++){
        sum += arr[i];
        if(sum == target){
            maxLength = max(maxLength , i + 1);
        }
        int rem = sum - target;
        if(presummp.find(rem) != presummp.end()){
            int len = i - presummp[rem];
            maxLength = max(maxLength , len);
        }
        presummp[sum] = i;
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
    cout<<longestsubArr_with_Sum_K(arr , target );
    return 0;
}
```
# Complexity:
Time Complexity: O(1) map operations on average).
Space Complexity: O(n) (storage of prefix sums).





