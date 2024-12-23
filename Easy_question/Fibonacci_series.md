# Fibonacci Series..
Problem Statement: Given an integer N. Print the Fibonacci series up to the Nth term.

Examples:

Example 1:
# Input: 
```N = 5```
# Output: 
```0 1 1 2 3 5```

Explanation: 0 1 1 2 3 5 is the fibonacci series up to 5th term.(0 based indexing)

Example 2:
# Input: 
```6```
# Output: 
```0 1 1 2 3 5 8```

Explanation: 0 1 1 2 3 5 8 is the fibonacci series upto 6th term.(o based indexing)

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
int fib(int n , vector<int>& memo){
    if(n <= 1) return n;
    if(memo[n] != -1){
        return memo[n];
    }
   memo[n] = fib(n-1, memo) + fib(n-2 , memo);
   return memo[n];
}
int main() {
   int n;
   cin>>n;
   
   vector<int> memo(n+1 , -1);
 
   for(int i =0 ;i<n ;i++){
       cout<<fib(i , memo)<<" ";
   }
   cout<<endl;
    return 0;
}
```
# Complexity
Time Complexity : O(n)

Space Complexity : O(n)