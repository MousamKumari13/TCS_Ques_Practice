# Check the number is prime or not

Problem Statement: Given an integer N, check whether it is prime or not. A prime number is a number that is only divisible by 1 and itself and the total number of divisors is 2.

Examples
Example 1:
# Input:
```N = 2```
# Output:True
Explanation: 2 is a prime number because it has two divisors: 1 and 2 (the number itself).
Example 2:
# Input:
```N =10```
# Output: False
Explanation: 10 is not prime, it is a composite number because it has 4 divisors: 1, 2, 5 and 10.

# problem Link _
https://www.naukri.com/code360/problems/check-prime_624934?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
bool isprime(int n){
    if(n <= 1) return false;
    
    for(int i =2 ;i <= sqrt(n) ;i++){
        if(n % i == 0){
            return false;
        }
    }
    return true;
}
int main() {
   int num ;
   cin>>num;
   
  if(!isprime(num)){
      cout<<"False"<<endl;
  }else{
      cout<<"True"<<endl;
  }
    return 0;
}
```
# Complexity Analysis
Time Complexity: 𝑂(Root n)
Only checks divisors up to.

Space Complexity: O(1)
Constant space is used.