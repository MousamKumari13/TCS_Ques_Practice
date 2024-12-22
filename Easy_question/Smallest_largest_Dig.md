# Smallest and largest digits present in the number.
Problem Statement: Given a number N, print the smallest and largest digits present in the number.

Examples:

Example 1:
# Input: 
```N = 2746```
# Output: 
 ```Largest digit: 7```
 ```Smallest digit: 2```

Explanation: By simply going through the digits of 
the number, we figure out the largest and smallest 
digit in the number.

Example 2:
# Input: 
```N = 23004```
# Output: 
```Largest digit : 4```
```Smallest digit : 0```
Explanation: By simply going through the digits of 
the number, we figure out the largest and smallest 
digit in the number.

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void Smallest_Largest_Dig(int n){
    int smalestDig = INT_MAX;
    int Largest_Dig = INT_MIN;
    while(n >0){
        int dig = n % 10;
        smalestDig = min(smalestDig , dig);
        Largest_Dig = max(Largest_Dig , dig);
        n /= 10;
    }
    
    cout<<"Largest digit:" <<Largest_Dig<<endl;
    cout<<"Smallest digit: " <<smalestDig<<endl;
}
int main() {
   int n;
   cin>>n;
   
   Smallest_Largest_Dig(n);
    return 0;
}
```
# Complexity
Time Complexity: O(log 10(n))

Space Complexity: O(1)