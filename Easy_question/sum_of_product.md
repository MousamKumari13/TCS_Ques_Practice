# calculate the "modified sum" of a given number n. The modified sum is defined as the sum of the products of n and each integer from 1 to n.

Input:
A single integer 
```n (1 ≤ n ≤ 100).```
Output:
Print the modified sum as a single integer.
Example:
## Input:
```3```
## Output:
```18```
Explanation:
For 
n=3:
The modified sum is calculated as:
3×1+3×2+3×3=3+6+9=18.

# Solution
``` C++

#include <bits/stdc++.h>
using namespace std;

int main()
{
   int n;
   cin>>n;
   int sum =0;
   
   for(int i = 1 ; i<= n ;i++){
       sum += n*i;
   }
   cout<<sum<<endl;
    return 0;
}
```
