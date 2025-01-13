# The maximum product that can be obtained by multiplying three numbers from the array. The array may contain both positive and negative integers.
You are given an array of integers. Your task is to find the maximum product that can be obtained by multiplying three numbers from the array. The array may contain both positive and negative integers.

The result can either be the product of the three largest numbers or the product of the two smallest (most negative) numbers and the largest number (this accounts for the case where multiplying two negative numbers results in a positive product).
Write a program to calculate and print the maximum product.

Input:
An integer N, representing the number of elements in the array.
An array arr of N integers.
Output:
Return the maximum product of any three integers from the array.
Example 1:
## Input:
```6```
```-10 -10 5 2 3 1```
## Output:
```500```

Explanation:
The maximum product is obtained by multiplying -10 * -10 * 5 = 500.

Example 2:
## Input:
```4```
```1 2 3 4```
## Output:
```24```

Explanation:
The maximum product is obtained by multiplying 4 * 3 * 2 = 24.

# solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void productOfmaxThreenum(vector<int>&  arr ){
   int n = arr.size();
   sort(arr.begin() , arr.end());
  
  int product1 = arr[n-1] * arr[n-2] * arr[n-3];
  int product2 = arr[0] * arr[1] * arr[n-1];
  
  if(product1 > product2){
      cout<<product1<<endl;
  }else{
      cout<<product2<<endl;
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
    
  productOfmaxThreenum(arr);
    return 0;
}
```
## complexity
Time Complexity:  ```O(NlogN)```, where N is the size of the array.

Space Complexity: ``` O(N)``` for storing the input array.
