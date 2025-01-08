# Capitalize the first and last character of each word.
Problem Statement: Given a string, write a program to Capitalize the first and last character of each word of that string.

Examples:

Example 1:
## Input: String str = 
```"take u forward is awesome"```
## Output: 
```“TakE U ForwarD IS AwesomE”```
Explanation: We get the result after capitalizing the first and last character of each word of a string

Example 2:
## Input: String str = 
```"Take u Forward is Awesome"```
## Output: 
```“TakE U ForwarD IS AwesomE”```
Explanation: Characters T, F, A are initially in uppercase , so they remain as they are in the result.

# Solution
```C++

#include <bits/stdc++.h>
using namespace std;
string capatalize(string str){
    int n= str.length();
    for(int i = 0 ;i<n ;i++){
        if(i == 0 || str[i-1] == ' '){
            str[i] = toupper(str[i]);
        }
        if(i == n-1 || str[i+1] == ' '){
            str[i] = toupper(str[i]);
        }
    }
    return str;
}
int main()
{
   string str;
   getline(cin, str);
   cout<<capatalize(str);
    return 0;
}
```
# Complexity
Time Complexity: O(n), where n is the length of the string (as each character is processed once).

Space Complexity: O(1), since the operations are done in place.