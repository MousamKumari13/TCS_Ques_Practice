## Find  the 15th term of the series?
``` 0,0,7,6,14,12,21,18, 28 ```
Explanation :
In this series the odd term is increment of  ``` 7 {0, 7, 14, 21, 28, 35 – – – – – – } ```
And even term is a increment of  ```6 {0, 6, 12, 18, 24, 30 – – – – – – }```

## input 
``` 15 ```

## output
``` 42 ```

# Solution 

``` c++ 
#include <bits/stdc++.h>
using namespace std;
int solve(int n){
    if(n%2 == 0){
         return 7* (n+1 /2);
    }else{
        return 6*(n/2);
    }
}
int main() {
   int n;
   cin>>n;
   cout<<solve(n)<<endl;
    return 0;
}
