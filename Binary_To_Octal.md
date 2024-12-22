# Binary To Octal
Problem Statement: Convert a binary number to an octal number

Examples:

Example 1:.
# Input: 
```N = 1100110```
# Output: 
```146```
Explanation: 1100110 when converted to octal number is “146”.

Example 2:
# Input: 
```11111```
# Output: 
```37```
Explanation: 11111 when converted to octal number is “37”.

# Soltion 
```C++

#include<bits/stdc++.h>
using namespace std;

int main() {
    int bn ;
    cin>>bn;
    int octal =0 , decimal =0 , i =0;
    
    while(bn !=0){
        decimal += (bn % 10) * pow(2 , i);
        i++;
        bn /= 10;
    }
    
    i = 1;
    while(decimal !=0){
        octal += (decimal % 8) * i;
        decimal /= 8;
          i *=10;
    }
    
    cout<<octal<<endl;
   return 0;
}
```
# Complexity
Conclusion
Time Complexity: O(k⋅log 2 (k)), where 𝑘 is the number of digits in the binary input.

Space Complexity: O(1).