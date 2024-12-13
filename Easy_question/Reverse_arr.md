# Reverse an Array

Problem Statement: You are given an array. The task is to reverse the array and print it. 

Examples:

Example 1:
# Input:
``` N = 5, arr[] = {5,4,3,2,1}```
# Output: 
```{1,2,3,4,5}```
Explanation: Since the order of elements gets reversed the first element will occupy the fifth position, the second element occupies the fourth position and so on.

Example 2:
# Input:
``` N=6 arr[] = {10,20,30,40} ```
# Output:
``` {40,30,20,10}```
Explanation: Since the order of elements gets reversed the first element will occupy the fifth position, the second element occupies the fourth position and so on.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void Reverse(int n , vector<int>& arr){
     int i =0 , j = n-1;
       while(i < j){
           swap(arr[i] , arr[j]);
           i++;
           j--;
       }
   
   for(int k =0 ;k<n ;k++){
      cout<<arr[k]<<" ";
   }
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
  
   Reverse(n , arr);
    return 0;
}
```