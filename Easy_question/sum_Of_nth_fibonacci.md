# Calculate the sum of the first  n Fibonacci numbers.
The Fibonacci sequence is defined as:
F(0)=0, 
F(1)=1
F(n)=F(n−1)+F(n−2) for n≥2.
Your task is to compute the sum of the first n Fibonacci numbers.

Input: A single integer n (n≥0).
Output:
The sum of the first n Fibonacci numbers.

Constraints:
0≤n≤30.
Example:
## Input:
```5```
## Output:
```12```
Explanation:
The first 5 Fibonacci numbers are: 
0,1,1,2,3.
Their sum is 
0+1+1+2+3=12.

# Solution(Recursive)
```C++

#include <bits/stdc++.h>
using namespace std;

int fib(int n){
    if(n <= 1) return n;
     if (memo[n] != -1) return memo[n];

    return memo[n]  = fib(n-1) + fib(n-2);
}
int main()
{
    int n;
    cin>>n;

    if (n < 0) {
        cout << "Invalid input! n should be a non-negative integer." << endl;
        return 0;
    }
    
    memo.resize(n + 1, -1);

    int sum =0;
    fib(n);
    for(int i = 1 ;i<n ;i++){
          sum += fib(i);
    }
    cout<<sum<<endl;
    return 0;
}
```
# Complexity

Time Complexity : ```O(n) ```
The fib(n) function is implemented recursively, leading to exponential time complexity, specifically T(n)=O(2^n ).
This inefficiency arises because the function recomputes results for the same inputs repeatedly.

Space Complexity: ```O(n)```
Each recursive call in fib(n) adds a frame to the call stack.
The maximum depth of recursion is n, so the space complexity is:


# Solution(iterative)
```C++
#include <bits/stdc++.h>
using namespace std;

int fib(int n) {
    if (n <= 1) return n; // Base case
    int prev2 = 0, prev1 = 1, current;
    for (int i = 2; i <= n; i++) {
        current = prev1 + prev2;
        prev2 = prev1;
        prev1 = current;
    }
    return current;
}

int main() {
    int n;
    cin >> n;

    if (n < 0) {
        cout << "Invalid input! n should be a non-negative integer." << endl;
        return 0;
    }

   
    int sum =0;
    fib(n);
    for(int i = 1 ;i<n ;i++){
          sum += fib(i);
    }
    cout<<sum<<endl;

    return 0;
}
```
# Overall Complexity
Time Complexity: O(n)
Space Complexity: O(1)
