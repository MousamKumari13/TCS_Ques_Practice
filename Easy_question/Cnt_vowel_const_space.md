# Count the number of vowels, consonants, and spaces.

Problem Statement: Given a string, write a program to count the number of vowels, consonants, and spaces in that string.

Examples:

Example 1:
# Input: 
```string str=”Take u forward is Awesome”```
# Output: 
```Vowels: 10```
```Consonants: 11```
```White spaces: 4``
`
# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void count(string & s){
    int vowel =0  , consonant =0 , whitespce = 0;
    
    for(char ch : s){
        if(isspace(ch)){
            whitespce++;
        }else if(isalpha(ch)){
            char lower = tolower(ch);
            if(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ){
                vowel++;
            }else{
                consonant++;
            }
        }
    }
    cout<<"Vowels :" <<vowel<<endl;
    cout<<"Consonant :"<<consonant<<endl;
    cout<<"Whitespace :"<<whitespce<<endl;
}
int main() {
    string str;
    getline(cin, str);
    
    count(str);
    return 0;
}
```
# Complexity
Time Complexity: O(n), where n is the length of the input string.

Space Complexity: O(1).