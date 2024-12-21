# Binary To Decimal

Problem Statement: Convert a binary number to a decimal number.

Examples:

Example 1:
# Input: 
```N = 1011```
# Output: 
```11```
Explanation: 1011 when converted to decimal number is “11”.

Example 2:
# Input: 
```100```
# Output: 
```4```
Explanation: 100 when converted to decimal number is “4”.

# Solution 
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    string s;
    cin>>s;
	int n = s.length();
	int base = 1;
	int ans = 0;
	for (int i = n - 1; i >= 0; i--) {
		if (s[i] == '1') {
			ans += base;
		}
		base *= 2;
	}
	cout << ans;
}
```
# Complexity
Time Complexity: O(N).

Space Complexity: O(1).