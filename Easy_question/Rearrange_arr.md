# Rearrange array in increasing-decreasing order
Problem Statement:
 Rearrange the array such that the first half is arranged in increasing order, and the second half is arranged in decreasing order

# Examples:

Example 1:
# Input:
``` 8 7 1 6 5 9 ```
# Output:
``` 1 5 6 9 8 7```
Explanation: First three elements are in the ascending order and next three elements are in the descending order.

Example 2:
# Input:
``` 4 2 8 6 15 5 9 20```
# Output: 
```2 4 5 6 20 15 9 8```

# Solution 
# 1st Approach
``` C++ 
#include <bits/stdc++.h>
using namespace std;
void rearrange(int n , vector<int>& arr){
    sort(arr.begin() , arr.end());
    vector<int> temp(n);
    for(int i = 0 ;i < n/2 ;i++){
        temp.push_back(arr[i]);
    }
    int j = n-1;
    for(int i = n/2 ;i< j ;i++){
        swap(arr[i], arr[j]);
        j--;
        temp.push_back(arr[j]);
    }
    for(int i=0 ;i<n ;i++){
        cout<<arr[i]<<" ";
    }
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   rearrange(n , arr);
    return 0;
}
```
# Solution 
# 2nd Approach
``` C++
#include <bits/stdc++.h>
using namespace std;
void rearrange(int n , vector<int>& arr){
      sort(arr.begin() , arr.end());
      vector<int> firsthalf(arr.begin() , arr.begin()+ n/2);
      vector<int> secondhalf( arr.begin()+n/2 , arr.end());
      
      reverse(secondhalf.begin() , secondhalf.end());
      firsthalf.insert(firsthalf.end(), secondhalf.begin(), secondhalf.end());
      
      for(int num : firsthalf){
          cout<<num<<" ";
      }
      cout<<endl;
      
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   rearrange(n , arr);
    return 0;
}
```