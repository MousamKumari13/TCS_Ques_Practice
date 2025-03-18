# Problem Statement: Range Sum Query
You are given two integers i and j, where 0 Si < j≤ 9999. Your task is to compute the sum of integers from index i to j, both included.
## Input Format:
two integers i and j (0 Si < j ≤ 9999).
## Output Format:
For each query, print a single integer representing the sum of numbers from index i to j.
**Constraints:**
```plaintext
0≤i<j≤ 9999
```
## Input :
```plaintext
0 3
26
10 10001
```
## Output :
```plaintext
6
20
Invalid input ilj i <= j < 10000
```
# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int t;
    cin>>t;
    while(t--){
       int i , j;
        cin>>i >>j;
       int sum =0;
  
       if(i > j || j > 9999){
          cout<<"Invalid input i&j i <= j < 10000"<<endl;
         }
   
      else{
        sum = (j * (j+1) / 2) - (i * (i-1) /2);
         cout<<sum<<endl;
       }
    }
    return 0;
}
```
# Overall Complexity
👉 O(t) ≈ O(1) per query (since input constraints are small). 🚀
