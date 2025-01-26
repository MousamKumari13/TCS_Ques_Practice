 # Reverse string Word Wise

***Problem statement***
Reverse the given string word wise. That is, the last word in given string should come at 1st place, last second word at 2nd place and so on. Individual words should remain as it is.

**Constraints :**
```0 <= |S| <= 10^7```
where |S| represents the length of string, S.

### Sample Input 1:
```plaintext
Welcome to Coding Ninjas
```
### Sample Output 1:
```plaintext
Ninjas Coding to Welcome
```
### Sample Input 2:
```plaintext
Always indent your code
```
### Sample Output 2:
```plaintext
code your indent Always
```

## Problem link ->
https://www.naukri.com/code360/problems/reverse-string-word-wise_624402?interviewProblemRedirection=true&search=Reverse&leftPanelTabValue=PROBLEM&count=25&page=2&sort_entity=order&sort_order=ASC&customSource=studio_nav

## Solution
```C++
#include <bits/stdc++.h> 
using namespace std;

void reverseStringWordwise(string& str){
    int size = str.length();
    
    string ans = "";
    string curr = "";
    
    for(int i = size-1; i >= 0 ; i--){
        if(str[i] != ' '){
            curr = str[i] + curr;
        }else{
            ans = ans + curr + ' ';
            curr = "";
        }
    }
    ans = ans + curr;
    str = ans;
}
int main()
{
   string str;
   getline(cin , str);
   
   reverseStringWordwise(str);
   
   cout<<str;;
    return 0;
}
```
## Complexity Analysis

**Time Complexity:** ```O(n)``` Traversing the string once to reverse words.


**Space Complexity:** ```O(n)``` Using auxiliary strings ans and curr.