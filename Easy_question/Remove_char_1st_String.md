# program to remove characters from the first string which are present in the second string.

Problem Statement: Given two strings, write a program to remove characters from the first string which are present in the second string.

Examples:

Example 1:
## Input: 
``String str1 = “abcdef”```
```String str2 = “cefz”```
## Output: 
```abd```

Explanation: The common characters in both strings are c, e, f.
So after removing these characters from string 1 we get string resulting string as abd.


Example 2:
## Input: 
```String str1 = “xyzpw”```
```String str2 = “lmno”```
## Output: 
```xyzpw```

Explanation: As there is no common character in both the strings, string 1 remains unchanged.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void removeString(string str1 , string str2){
    unordered_set<char> charStr2;
    
    for(char ch: str2){
        charStr2.insert(ch);
    }
    string result = "";
    for(char ch : str1){
        if(charStr2.find(ch) == charStr2.end()){
            result += ch;
        }
    }
    cout<<result<<endl;
}

int main()
{
    string str1 , str2;
    cin>>str1>>str2;
    removeString(str1 , str2);
    
    return 0;
}
```
# Complexity:
Time Complexity: O(n + m).
Building the set: O(m), where m is the length of str2.
Iterating through str1: O(n), where n is the length of str1.

Space Complexity: Unordered set for str2: O(m).