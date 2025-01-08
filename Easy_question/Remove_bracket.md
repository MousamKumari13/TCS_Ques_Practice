# “Remove brackets from an algebraic expression”

Problem Statement: 

Remove brackets from an algebraic expression

Write a program to remove brackets from an algebraic expression

Given an algebraic expression, we need to simplify the expression and remove the brackets.

Examples:

Example 1:
## Input:
``` “a+((b-c)+d)”```
## Output: 
```“a+b-c+d”```
Explanation: Removed all the brackets in the algebric expression.

Example 2:
## Input: 
```“(((a-b))+c)”```
## Output: 
```“a-b+c”```
Explanation: Removed all the brackets in the algebric expression.

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void removebracket(string str){
    int n = str.length();
    string result = "";
    for(int i =0 ;i<n ;i++){
        if(str[i] == '(' && str[i]== ')'){
            i++;
        }
        else if(str[i] != '(' && str[i] != ')'){
            result +=str[i];
        }
    }
   cout<<result;
}
int main()
{
   string str;
   cin>>str;
   removebracket(str);
    return 0;
}
```
# Complexity 
Time complexity = o(n)
Space complexity = O(n)

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

void removeBrackets(string str) {
    string result = "";
    for (char ch : str) {
        if (ch != '(' && ch != ')') {
            result += ch;
        }
    }
    cout << result;
}

int main() {
    string str;
    cin >> str;
    removeBrackets(str);
    return 0;
}
```
# Complexity 
Time complexity = o(n)
Space complexity = O(n)