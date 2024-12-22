# Maximum Product SubArray
Problem Statement: Given an array that contains both negative and positive integers, find the maximum product subarray.

Examples
Example 1:
# Input:

``` Nums = [1,2,3,4,5,0]```
# Output:

 ```120```

Explanation:
 In the given array, we can see 1×2×3×4×5 gives maximum product value.


Example 2:
# Input:
 ```Nums = [1,2,-3,0,-4,-5]```

# Output:

``` 20```

# Problem Link ->
https://www.naukri.com/code360/problems/subarray-with-maximum-product_6890008?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse

# Solution (Brut force Approach)
```C++

#include <bits/stdc++.h>
using namespace std;
int MaxProductSubarr(vector<int> & arr , int n){
    int result = INT_MIN;
    for(int i =0 ;i< n-1 ;i++){
        for(int j = i+1 ; j< n ;j++){
             int prod = 1;
            for(int k = i ; k<= j ;k++){
               prod *= arr[k];
               result = max(result , prod);
            }
        }
    }
    return result;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }
   
   cout<< MaxProductSubarr(arr , n)<<endl;
    return 0;
}
```
# Complexity

Time Complexity: O(N^3)

Reason: We are using 3 nested loops for finding all possible subarrays and their product.

Space Complexity: O(1)

Reason: No extra data structure was used

# Solution (Better Approach)

```C++
#include <bits/stdc++.h>
using namespace std;
int MaxProductSubarr(vector<int> & arr , int n){
    int result = arr[0];
    
    for(int i =0 ;i< n-1 ;i++){
        int p = arr[i];
        for(int j = i+1 ;j<  n ;j++){
            result = max( result , p);
            p *= arr[j];
        }
        result = max(result , p); // manages (n-1)th term
    }
    
    return result;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }
   
   cout<< MaxProductSubarr(arr , n)<<endl;
    return 0;
}
```
# Complexity Analysis

Time Complexity: O(N2)

Reason: We are using two nested loops

Space Complexity: O(1)

Reason: No extra data structures are used for computation

# Solution (Optimal Approach)

```C++
#include <bits/stdc++.h>
using namespace std;
int MaxProductSubarr(vector<int> & arr , int n){
    int ans = INT_MIN;
    
    int pre = 1 , suff = 1;
    
    for(int i =0 ;i< n ;i++){
        if(pre == 0) pre = 1;
        if(suff == 0) suff = 1;
        
        pre *= arr[i];
        suff *= arr[n-i-1];
        
        ans = max(ans , max(pre, suff));
    }
    return ans;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }
   
   cout<< MaxProductSubarr(arr , n)<<endl;
    return 0;
}
```
# Complexity Analysis

Time Complexity: O(N), N = size of the given array.
Reason: We are using a single loop that runs for N times.

Space Complexity: O(1) as No extra data structures are used for computation.

