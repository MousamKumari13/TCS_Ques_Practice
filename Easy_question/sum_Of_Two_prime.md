# Problem: Given a number n, express the number as a sum of 2 prime numbers.

Examples:

Example 1:
## Input : 
``N = 74```
## Output : 
```True ```. 
Explanation: 74 can be expressed as 71 + 3 and both are prime numbers. 

Example 2:
## Input :
```N = 11```
## Output : 
```False.``` 
Explanation: 11 cannot be expressed as sum of two prime numbers

## Solution 
```C++

#include <bits/stdc++.h>
using namespace std;
bool isprime(int n){
    if(n <= 1) return false;
    for(int i = 2 ;i<= sqrt(n) ;i++){
        if(n % i == 0) return false;
    }
    return true;
}
bool sumofTwoprime(int n){
    for(int i = 2; i <= n/2 ;i++){
        if(isprime(i) && isprime(n-i)){
            return true;
        }
    }
    return false;
}

int main()
{
   int n ;
   cin>>n;
   
   if(sumofTwoprime(n)){
       cout<<"True"<<endl;
   }else{
       cout<<"False"<<endl;
   }
    return 0;
}
```
# Complexity:
Time Complexity: O(n/2).
Space Complexity: O(1), as no additional data structures are used.