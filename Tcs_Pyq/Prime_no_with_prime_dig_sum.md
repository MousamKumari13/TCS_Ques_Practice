# Find Prime Numbers with Prime Digit Sum

Write a program to find all prime numbers in a given range [n, m] such that the sum of their digits is also a prime number.

Input:

Two integers n and m where ```n≤m.```
Output: Print all numbers in the range ```[n, m]``` that satisfy the following conditions:

The number itself is a prime number.
The sum of its digits is also a prime number.
Constraints:
```1≤n≤m≤10 ^6```

The program should efficiently check for prime numbers and their digit sums.
Example 1:

## Input:
```10 20```
## Output:
```11```
```13```
Explanation:

Prime numbers in the range ```[10, 20] are 11, 13, 17, 19.```
Among these:
The sum of digits of ```11``` is ```1+1=2,``` which is prime.
The sum of digits of ```13``` is  ```1+3=4,``` which is not prime.
The sum of digits of ```17``` is   ```1+7=8,``` which is not prime.
The sum of digits of ```19``` is  ```1+9=10,``` which is not prime.
Hence, only ```11``` and ```13``` are valid.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
bool isprime(int n){
    if(n < 2) return false;
    for(int  i=2 ; i< sqrt(n) ;i++){
        if(n % i == 0) return false;
    }
    return true;
}
int digitSum(int n){
    int sum =0;
    
    while(n > 0){
           sum += n % 10;
            n /= 10;
    }
    return sum;
}
void primeInRange(int min , int max){
    
    vector<int> result;
    
    for(int i = min ; i <= max ;i++){
         
        if(isprime(i)){
            int sum = digitSum(i);
            if(isprime(sum)){
                
                 result.push_back(i);
            }
            
        }
    }
     
    for(int i =0 ;i < result.size() ;i++){
        cout<<result[i]<<endl;
    }
   
}
int main()
{
   int min , max;
   cin>>min>>max;
   primeInRange(min , max);
    return 0;
}
```

# Complexity

Time Complexity:

O((m−n+1)⋅√k)
Where: m−n+1 : Total numbers in the range.

k : Time to check primality of each number and its digit sum (where k is the number's value).
For small digit sums, √k dominates.


Space Complexity : O(1)

