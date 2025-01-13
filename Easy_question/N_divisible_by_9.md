# checks if a given three-digit number is divisible by 9.
Question: Write a C++ program that checks if a given three-digit number is divisible by 9. The program should take an integer input from the user and print whether the number is divisible by 9 or not.

Input: A three-digit integer (between 100 and 999 inclusive).
Output: Print "Number <input_number> is divisible by 9" if the number is divisible by 9, otherwise print "Number <input_number> is not divisible by 9".
Example Input/Output:

## Input: 
```225```
## Output: Number 225 is divisible by 9

## Input: 
```237```
## Output: Number 237 is not divisible by 9

## Solution
```C++
#include<bits/stdc++.h>
using namespace std;


int main(){
  
  int n;
  cin>>n;
 
 if(n % 9 == 0){
     cout<<"Number "<<n<<" is divisible by 9";

 }else{
     cout<<"Number "<<n<<" is not divisible by 9";

 }
  return 0;

}
```
