# Prime Number In Range..
Problem Statement: Given a and b, find prime numbers in a given range [a,b], (a and b are included here).

Examples:

Examples:
# Input: 
```2 10```
# Output: 
```2 3 5 7 ```

Explanation: Prime Numbers b/w 2 and 10 are 2,3,5 and 7.

Example 2:
# Input: 
```10 16```
# Output: 
```11 13 ```

Explanation: Prime Numbers b/w 10 and 16 are 11 and 13.

# Solution
``` C++

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
void range(int min , int max){
    vector<int> prime;
    for(int i = min ; i<= max ;i++){
        if(isprime(i)){
            prime.push_back(i);
        }
    }
    
    for(int i =0 ;i< prime.size() ;i++){
        cout<<prime[i]<<" ";
    }
    cout<<endl;
}
int main() {
   int min , max;
   cin>>min>>max;
   
   range(min , max);
  
    return 0;
}
```
# Complexity
Time Complexity (Worst Case): O(N^3/2), where N is the upper limit of the range (max).

Space Complexity:O(R), where R=max−min+1.