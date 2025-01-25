# Sum OR Product:
***Problem statement***
You are given a number ‘N’ and a query ‘Q.’ If ‘Q’ is 1, then you have to return the sum of all integers from 1 to ‘N,’ else if ‘Q’ is equal to 2 then you have to return the product of all integers from 1 to ‘N.’ Since the product can be very large, return it modulo ```10 ^ 9 + 7```.

For example

Given ‘N’ = 4, ‘Q’ = 1. 
Then the answer is 10 because the sum of all integers between 1 and 4 are 1, 2, 3, and 4. Hence 1 + 2 + 3 + 4 is equal to 10.

Constraints:
1 <= ‘T’ <= 10
1 <= ‘N’ <= 10^4
1 <= ‘Q’ <= 2
## Sample Input 1 :
```plaintext
2
4 1 
4 2
```
## Sample Output 1 :
```plaintext
10
24 
```
Explanation of the Sample Input 1:
In the first test case, the answer is 10 because all integers between 1 and 4 are 1, 2, 3, and 4. Hence 1 + 2 + 3 + 4 is equal to 10.


In the second test case, the answer is 25 because all integers between 1 and 4 are 1, 2, 3, and 4. Hence 1 * 2 * 3 * 4 is equal to 24.
## Sample Input 2 :
```plaintext
2
5 1
5 2 
```
## Sample Output 2 :
```plaintext
15
120
```
### problem link ->
https://www.naukri.com/code360/problems/sum-or-product_920478?topList=tcs-interview-questions&problemListRedirection=true&leftPanelTabValue=PROBLEM
## Solution 
```
#include <bits/stdc++.h>
using namespace std;

long long int sumOrProduct(long long int n, long long int q) {
    long long int sum1 = 0;
    long long int prod = 1;
    const int MOD = 1000000007;

    if (q == 1) {
        for (long long int i = 1; i <= n; i++) {
            sum1 += i;
        }
        return sum1;
    } else {
        for (long long int i = 1; i <= n; i++) {
            prod = (prod * i) % MOD;
        }
        return prod;
    }
}

int main() {
    long long int n, q;
    cin >> n>>q;

    long long int result = sumOrProduct(n, q);
    cout << "Result: " << result << endl;

    return 0;
}
```
## Overall Complexity
**Time Complexity:** O(n).

**Space Complexity:** O(1) (no additional data structures used).
