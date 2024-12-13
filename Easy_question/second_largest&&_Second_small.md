# Find the sesond smallest and second largest element from array.

Problem Statement: Given an array, find the second smallest and second largest element in the array. Print ‘-1’ in the event that either of them doesn’t exist.

Examples
Example 1:
# Input:
 ```[1,2,4,7,7,5]```
# Output:
    Second Smallest : 2
	Second Largest : 5
Explanation:
 The elements are as follows 1,2,3,5,7,7 and hence second largest of these is 5 and second smallest is 2

Example 2:
# Input:
``` [1] ```
# Output:
    Second Smallest : -1
	Second Largest : -1
Explanation:
 Since there is only one element in the array, it is the largest and smallest element present in the array. There is no second largest or second smallest element present.

# Solution
``` C++
#include <bits/stdc++.h>
using namespace std;
int Second_smallest(int n, vector<int>& arr){
    int min_ele = INT_MAX;
    int secodsmallest = INT_MAX;
    for(int i =0 ; i< n ;i++){
        if(arr[i] < min_ele){
             secodsmallest = min_ele;
             min_ele = arr[i];
        }else if(arr[i] < secodsmallest && arr[i] != min_ele){
            secodsmallest= arr[i];
        }
    }
    return secodsmallest;
}
int Second_largest(int n , vector<int>& arr){
    int max_ele = INT_MIN;
    int Secondlargest = INT_MIN;
    if(n > 2 ){
      for(int i =0 ; i< n ;i++){
        if(arr[i] > max_ele){
             Secondlargest = max_ele;
             max_ele = arr[i];
        }else if(arr[i] > Secondlargest && arr[i] != max_ele){
            Secondlargest = arr[i];
        }
      }
    }
    return Secondlargest;
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   int secodsmallestele = Second_smallest(n, arr);
   
    if (secodsmallestele == INT_MAX) {
        cout << "Second Smallest: -1" << endl;
    } else {
        cout << "Second Smallest: " << secodsmallestele << endl;
    }

    int Secondlargestele = Second_largest(n, arr);
    
    if (Secondlargestele == INT_MIN) {
        cout << "Second Largest: -1" << endl;
    } else {
        cout << "Second Largest: " << Secondlargestele << endl;
    }

    return 0;
}
```