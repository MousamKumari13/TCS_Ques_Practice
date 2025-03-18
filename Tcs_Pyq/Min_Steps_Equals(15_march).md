# Making Triplets Equal.

You are given a triplet of integer( p,q,r). You can perform the following operation any number of times. 
**Select any two numbers from the triplet.**
**Add 1 to both selected numbers.**
**Subtract 1 from the remaining number.**
```Your task is to determine the number of steps faeded to make all three numbers equal using the given operation```
***If not possible return -1.***
### Input:
A single integer T representing the number of test cases.
Each test case consists of three integers a, b, c.
Output:
For each test case, print number of steps if it is possible to make all three numbers equal; otherwise, print -1.
### Constraints:
1ST ≤10^4
## Example : 
```plaintext
3
1 2 3
4 4 4
2 2 8
```
## output:
```plaintext
-1
0
3
```
# Solution(BrutForce Approach)
```C++
#include <bits/stdc++.h>
using namespace std;

int min_Steps(int p , int q , int r){
    vector<int> v = {p , q , r};
    sort(v.begin() , v.end());
    
    if(v[0] == v[1] && v[1] == v[2]){
        return 0;
    }
    
    int steps =0 ;
    
    while(true){
        v[0]++;
        v[1]++;
        v[2]--;
        steps++;
        sort(v.begin(), v.end());
        
         if(v[0] == v[1] && v[1] == v[2]){
            return steps;
        }
        
        if((v[0] == v[1] && v[1] + 1 == v[2]) ||
            (v[1] == v[2] && v[0] + 1 == v[1])){
                return -1;
         }
    }
}

int main()
{
    int t;
    cin>>t;
    while(t--){
       int p , q , r;
        cin>>p >>q>>r;
  
       int result = min_Steps(p , q , r);
       cout<<result<<endl;
    }
    
    return 0;
}
```
# Optimal approach
```C++
#include <iostream>
#include <algorithm>
using namespace std;

void solve() {
    int T;
    cin >> T;
    while (T--) {
        int a, b, c;
        cin >> a >> b >> c;
        int sum = a + b + c;
        
        if (sum % 3 != 0) {
            cout << -1 << endl;
        } else {
            int maxVal = max({a, b, c});
            cout << (2 * maxVal - sum) / 2 << endl;
        }
    }
}

int main() {
    solve();
    return 0;
}
```
### Explaination
Divisibility by 3:

If we want to make all numbers equal, say x, then we need:
x + x + x = 3x = p + q + r
This means (p+q+r) should be divisible by 3 for it to be possible.
