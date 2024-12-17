# find the median of the given array.
Problem Statement: Given an unsorted array, find the median of the given array.

Examples:

Example 1:
# Input: ```[2,4,1,3,5]```

# Output: 3

Example 2:
# Input: ``` [2,5,1,7]```
# Output: 3.5

# Solution 
```C++

#include <bits/stdc++.h>
using namespace std;
double median(vector<int>& arr){
    int n = arr.size();
    sort(arr.begin() , arr.end());
    
    if(n % 2 != 0){
        return arr[n/2];
    }
    return  (arr[(n - 1) / 2] + arr[n / 2]) / 2.0;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);

   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }

  double result = median(arr);
  cout<<result<<endl;
    return 0;
}
```
# Complexity Analysis
Time Complexity: 𝑂(𝑛log⁡n) , due to sorting the array.
Space Complexity: O(1) for the sorting operation (ignoring input storage).