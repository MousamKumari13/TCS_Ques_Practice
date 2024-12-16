#  Palindrome Numbers in a given range
Problem Statement: Given a range of numbers, find all the palindrome numbers in the range.

Note: A palindromic number is a number that remains the same when its digits are reversed.OR  a palindrome is a number that reads the same forward and backward Eg: 121,1221, 2552

# Examples:

Example 1:
# Input: 
```min = 10 , max = 50```
# Output: 
```11 22 33 44 ```


Explanation: 11, 22, 33, 44 will remain the same when they read from forward or backward.

Example2:
# Input: 
```min = 100 , max = 150```
# Output: 
```101 111 121 131 141```


Explanation: 11, 22, 33, 44 will remain the same when they read from forward or backward.

# Solution

```C++

#include <bits/stdc++.h>
using namespace std;
bool ispalindrome(int num){
    int temp= num;
    int rev =0;
    while(temp > 0){
        rev = rev* 10 + temp %10;
        temp /= 10;
    }
    if(num == rev) return true;
    return false;
}
int main() {
   int min , max;
   cin>>min>>max;
   
   for(int i=min; i<=max; i++) {
        if(ispalindrome(i)) {
            cout<<i <<" ";
        }
   }
    return 0;
}
```
# Time Complexity: O(N)

# Space Complexity: O(1)