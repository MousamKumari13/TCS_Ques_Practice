# Single Number

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

## Example 1:
## Input: 
```plaintext
nums = [2,2,1]
```

## Output: 
```plaintext
1
```
### Example 2:

## Input: 
```plaintext
nums = [4,1,2,1,2]
```
## Output:
```plaintext
 4
```
### Example 3:

## Input: 
```plaintext
nums = [1]
```
## Output:
```plaintext
 1
 ```
  
### Problem link-> 
https://leetcode.com/problems/single-number/description/

# Solution 
``` C++
#include <bits/stdc++.h>
using namespace std;

void single(int n , vector<int>& arr){
    unordered_map<int , int> mp;
    
    for(int num : arr){
        mp[num]++;
    }
    for(auto it : mp){
     if(it.second == 1){
        cout<<it.first<<endl;
      }
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
    single(n , arr);
    return 0;
}
```
## Time Complexity : O(n)
## Overall Space Complexity: O(n)

# Solution
``` C++

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n;
    cin>>n;
    
    vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
   
   int ans=0;
   
   for(int i =0 ; i< n ;i++){
       ans = ans ^ arr[i];
   }
   
   cout<<ans<<endl;
    return 0;
}
```
