# Write a program to generate a new password based on the following rules:

Alphabets:

Shift each lowercase letter ('a'-'z') forward in the alphabet by a given integer value, wrapping around if necessary (i.e., after 'z', it continues from 'a').
Similarly, shift each uppercase letter ('A'-'Z') forward in the alphabet by the given value, wrapping around if necessary (i.e., after 'Z', it continues from 'A').
Digits:

Shift each numeric character ('0'-'9') forward by the given value, wrapping around if necessary (i.e., after '9', it continues from '0').
Special Characters:

Replace '@' with #.
Replace all other special characters with @.
Input Format
A string containing a mix of alphabets, digits, and special characters, which serves as the initial password.
An integer value for shifting characters.
Output Format
The generated password after applying the transformations.

Constraints
The input string can have up to 10^3 characters.
1≤shift value≤1000.
Examples
Example 1:
Input:
Enter input string: Abc123@
Enter value: 2
Output:
Output: Cde345#
Explanation:
'A' → 'C', 'b' → 'd', 'c' → 'e' (shifted by 2).
'1' → '3', '2' → '4', '3' → '5' (shifted by 2).
'@' → #.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void newpassword(string& str , int val){
    string res ="";
    val = val % 26;
   for(auto ch : str){
       if(islower(ch)){
           char newchar = 'a' +(ch - 'a' + val) % 26;
           res += newchar;
       }else if(isupper(ch)){
           int newch = 'A' + (ch - 'A' + val) % 26;
           res += newch;
       }else if(isdigit(ch)){
           int newint = '0' + (ch - '0' + val) % 10;
           res += newint;
       }else if(ch == '@'){
          res += '#';
      }
   }
   cout<<res<<endl;
}
int main()
{
    string str;
    cout<<"Enter input string:"<<endl;
    cin>>str;
    int value;
    cout<<"Enter value:"<<endl;
    cin>>value;
    newpassword(str , value);
    return 0;
}
```
## Complexity

Time Complexity: O(N) (linear in the length of the input string).


Space Complexity: O(N) (linear space for the input and output strings).