# Problem statement:
 Given an array, we have found the number of occurrences of each element in the array.

Examples:

Example 1:
# Input: 
```arr[] = {10,5,10,15,10,5};```
# Output:
    10  3
	 5  2
     15  1
Explanation: 10 occurs 3 times in the array
	      5 occurs 2 times in the array
              15 occurs 1 time in the array

Example2: 
# Input:
 ```arr[] = {2,2,3,4,4,2};```
# Output: 
   2  3
   3  1 
   4  2
Explanation: 2 occurs 3 times in the array
	     3 occurs 1 time in the array
             4 occurs 2 time in the array

# Solution 
``` C++
#include <bits/stdc++.h>
using namespace std;
void occurenceOfEle(int n , vector<int>& arr){
    unordered_map<int , int> mp;
    
    for(int num : arr){ // counting the frequency of each number and storing it into a map
        mp[num]++;
    }
    
    for(auto& pair : mp){
        cout<<pair.first<<" "<<pair.second<<endl; // acessing the first and second element of map
    }
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
  
  occurenceOfEle(n , arr);
    return 0;
}
```