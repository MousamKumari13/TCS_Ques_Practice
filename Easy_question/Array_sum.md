# Sum of All Element in Array

Problem Statement: Given an array, we have to find the sum of all the elements in the array.

# Examples:

Example 1:
# Input: 
```N = 5, array[] = {1,2,3,4,5}```
# Output: 
```15```

Explanation: Sum of all the elements is 1+2+3+4+5 = 15

Example 2:
# Input: 
``` N=6, array[] = {1,2,1,1,5,1}```

# Output:
``` 11```


Explanation: Sum of all the elements is 1+2+1+1+5+1 = 11

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void sum(int n , vector<int>& arr){
    int sum =0;
    for(int i=0 ;i<n ;i++){
        sum += arr[i];
    }
    
    cout<<sum<<endl;
}
int main() {
   int n ;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   sum(n , arr);
    return 0;
}
```