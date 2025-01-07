# Problem Statement: Adding two fractional numbers.

Examples:

Example 1:
## Input: 
```3/4 + 1/7 ```
## Output: 
```25/28```
Explanation: Since 3/4 + 1/7 = 25/28

Example 2:
## Input: 
```5/2 +1/2```
## Output: 
```3/1```
Explanation: Since 5/2 + 1/2 = 3/1

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

int gcd(int a , int b){
    if(b == 0) return a;
    return gcd(b , a % b);
}

void addFraction(int num1 , int denum1 , int num2, int denum2){
    int nume = num1* denum2  + num2 * denum1;
    
    int denume = denum1 * denum2;
   
    int commonDiv = gcd(nume , denume);
    nume /= commonDiv;
    denume /= commonDiv;
    
    cout<<nume<<"/"<<denume;
}

int main()
{
    int num1 , denum1 , num2 , denum2;
    cin>>num1>>denum1>>num2>>denum2;
    
    addFraction(num1 , denum1 , num2 , denum2);

    return 0;
}
```
# Complexity
 Time Complexity
Numerator and Denominator Calculation: O(1)
GCD Calculation: O(log(min(numerator,denominator)))
Overall: O(log(min(numerator,denominator)))

Space Complexity:
O(log(min(numerator,denominator)) (due to recursion).