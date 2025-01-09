# Problem Statement: Given a string, calculate the frequency of characters in a string.

Examples:

Example 1:
## Input: ```takeuforward```
## Output: ```a2 d1 e1 f1 k1 o1 r2 t1 u1 w1 ```
Explanation: Count of every character of string is printed.

Example 2:
## Input: ```articles```
## Output: ```a1 c1 e1 i1 l1 r1 s1 t1 ```
Explanation: Count of every character of string is printed

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void countfreq(string str){
    map<char , int> mp;
    for(char ch : str){
        mp[ch]++;
    }
    for(auto& ch : mp){
        cout<<ch.first<<ch.second<<" ";
    }
}
int main()
{
   string str;
   cin>>str;
   countfreq(str);
    return 0;
}
```

# Complexity
Time Complexity: O(nlogk) or O(n) for practical purposes.
Space Complexity: O(k) or O(1) for practical purposes.