# Consider the following series:
 ``` 1, 1, 2, 3, 4, 9, 8, 27, 16, 81, 32, 243, 64, 729, 128, 2187 …```

This series is a mixture of 2 series – all the odd terms in this series form a geometric series and all the even terms form yet another geometric series. Write a program to find the Nth term in the series.

The value N in a positive integer that should be read from STDIN. The Nth term that is calculated by the program should be written to STDOUT. Other than value of n th term,no other character / string or message should be written to STDOUT. For example , if N=16, the 16th term in the series is 2187, so only value 2187 should be printed to STDOUT.
You can assume that N will not exceed 30.
# Input
```N = 16 ```
# Output
```2187 ```
# Solution 

``` c++ 
#include <bits/stdc++.h>
using namespace std;

int main() {
   int n;
   cin>>n;
  
  if(n %2 == 1){ 
      int k = (n+1)/2;
      cout<<(int) pow(2 , k-1)<<endl;
  }else{
      int k = n/2;
     cout<<(int) pow(3 , k-1)<<endl;
  }
    return 0;
}
```
# Approach
If n is even then we calculate the power of 2 number 
dry run if n= 15
 15 % 2 = 1 goes in if condition
 then we have to caculate the nth term 
 k = (15 + 1) / 2 = 8
 the power of 2 ^8-1 = 2^7 = 128 

 #  BY using chatgpt (chat.openai.com)