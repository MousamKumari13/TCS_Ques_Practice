# Check if array is subset of another array.

## Write a program to find whether an array is a subset of another array or not.

Given arr1[] and arr2[], we need to find whether arr1[] is a subset of arr2[]. An array is called a subset of another if all of its elements are present in the other array.

Note: Array elements are assumed to be unique.

Examples:

Example 1:
# Input: 
```arr1[]= [1,3,4,5,2]```
```arr2[]= [2,4,3,1,7,5,15]```
# Output: 
```arr1[] is a subset of arr2[]```

Example 2:
# Input: 
```arr1[]= [1,3,4,5,2]```
```arr2[]= [4,5,2]```
# Output: 
```arr1[] is not a subset of arr2[]```

Example 3:
# Input: 
```arr1[]= [1,3,4,5,2]```
```arr2[]= [11,12,13,15,16]```
# Output: 
```arr1[] is not a subset of arr2[]```

# problem Link ->
https://www.geeksforgeeks.org/problems/array-subset-of-another-array2317/1?utm_source=youtube&utm_medium=collab_codein10_description&utm_campaign=array-subset

# Solution 
```C++

#include <bits/stdc++.h>
using namespace std;

string subset(int n , vector<int>& arr1 , int m , vector<int>& arr2){
   unordered_set<int> mp2(arr2.begin() , arr2.end());
   
   for(int i=0;i<n ;i++){
       if(mp2.find(arr1[i]) == mp2.end()){
           return "arr1[] is  not a subset of arr2[]";
       }
   }
   return "arr1[] is a subset of arr2[]";
    
}
int main()
{
    int n ;
    cin>>n;
    vector<int> arr1(n);
    
    for(int i =0 ;i<n ;i++){
        cin>>arr1[i];
    }
    
    int m ;
    cin>>m;
    vector<int> arr2(m);
    
     
    for(int i =0 ; i< m ; i++){
        cin>>arr2[i];
    }
    
    string result = subset(n , arr1 , m , arr2);
    cout<<result;

    return 0;
}
```
# Complexity
Overall Time Complexity: O(m+n)

space complexity : The unordered_set requires O(m) additional space to store elements of arr2.