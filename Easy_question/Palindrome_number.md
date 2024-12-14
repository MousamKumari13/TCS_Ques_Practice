# Palindrome Number
Problem Statement:
 Given an integer N, return true if it is a palindrome else return false.

A palindrome is a number that reads the same backward as forward. For example, 121, 1331, and 4554 are palindromes because they remain the same when their digits are reversed.

Examples
Example 1:
# Input:
```N = 4554```
# Output: Palindrome Number


Explanation: The reverse of 4554 is 4554 and therefore it is palindrome number
Example 2:
# Input:
```N = 7789```
# Output: Not Palindrome


Explanation: The reverse of number 7789 is 9877 and therefore it is not palindrome

# Question Link - https://leetcode.com/problems/palindrome-number/description/

# Solution
``` C++
#include <bits/stdc++.h>
using namespace std;
bool ispalindrome(int num){
    int orgnum = num;
    int rev =0;
    while(num > 0){
        int dig = num % 10;
        rev = rev* 10 + dig;
        num /= 10;
    }
    return rev = orgnum;
}
int main() {
   int n;
   cin>>n;
   
   if(ispalindrome(n)){
       cout<<"Palindrome Number"<<endl;
   }else{
       cout<<"Not Palindrome"<<endl;
   }
    return 0;
}
```
# Complexity
Time Complexity: O(logn)

Space Complexity: 𝑂(1)