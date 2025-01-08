# Octal To Decimal Conversion
Problem Statement: Given an Octal Number, convert it into a Decimal Number.

Examples:

Example 1:
## Input: 
```345```
## Output: 
```229```

Explanation: Decimal equivalent of given Octal expressionis 229

Example 2:
## Input: 
```170```
## Output: 
```121```

Explanation: Decimal equivalent of given Octal expression is121

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void octalTODecimal(int octal){
    int result = 0 , i =0;
    while(octal > 0){
        result += (octal %10) * pow(8 , i);
        i++;
        octal /=10;
    }
    cout<<result;
}
int main()
{
   int num;
   cin>>num;
   octalTODecimal(num);
    return 0;
}
```
## Complexity
Time Complexity: O(n) where n is the number of digits in the Octal Number.

Space Complexity: O(1)