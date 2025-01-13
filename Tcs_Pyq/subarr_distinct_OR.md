 # The total number of distinct values that can be obtained by performing a bitwise OR operation on all possible subarrays of the array.
Given an array of integers, write a program to find the total number of distinct values that can be obtained by performing a bitwise OR operation on all possible subarrays of the array.

Definitions:
A subarray is a contiguous part of an array.
The bitwise OR operation compares corresponding bits of two integers and sets each bit to 1 if at least one of the bits is 1.
Input:
The first line contains an integer n (1≤n≤10^5 ), the size of the array.
The second line contains 
n integers (0≤array elements≤10^9 ), the elements of the array.
Output:
Print a single integer, the count of distinct values obtained from the bitwise OR operations on all possible subarrays.
Example:
## Input:
```3 ```
```1 2 3  ```
## Output:
```6  ```
Explanation:
All possible subarrays of [1,2,3]:
[1]: OR = 1
[2]: OR = 2
[3]: OR = 3
[1,2]: OR = 1 | 2 = 3
[2,3]: OR = 2 | 3 = 3
[1,2,3]: OR = 1 | 2 | 3 = 3
Distinct values: {1,2,3}. Total = 6.

# solution
```C++
#include <bits/stdc++.h>
using namespace std;

int bitwiseOradd(vector<int>& a) {
    int n = a.size();
    set<int> st, prev;

    for (int i = 0; i < n; i++) {
        set<int> curr;
        curr.insert(a[i]);
        for (int val : prev) {
            curr.insert(val | a[i]);
        }
        prev = curr;
        st.insert(curr.begin(), curr.end());
    }

    int add = 0;
    for (int val : st) {
        add += val;
    }
  return add;
}

int main()
{
    int n;
    cin>>n;
    vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
   
   cout<<bitwiseOradd(arr)<<endl;
    return 0;
}
```
# Complexity
Time Complexity: O(n×k), effectively O(n) for practical scenarios.

Space Complexity: O(n).






