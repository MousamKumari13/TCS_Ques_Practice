# A program to sort characters.
Problem Statement:  Write a program to sort characters (numbers and punctuation symbols are not included) in a given string.

Examples:

Example 1:
## Input: 
```String str = “zxcbg”```
## Output: 
```bcgxz```

Explanation: After sorting we get string as bcgxz

Example 2:
## Input: 
```String str = “edcba”```
## Output: 
```abcde```

Explanation: After sorting we get string as abcde

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void sortChar(string str){
    int freq[26] = {0};
    
    for(char ch: str){
        freq[ch - 'a']++;
    }
    int index = 0;
    for(int i =0 ;i<26 ;i++){
        if(freq[i] >0){
            str[index++] = 'a' + i;
            freq[i]--;
        }
    }
    cout<<str<<endl;
}
int main()
{
    string str;
    cin>>str;
    sortChar(str);
    return 0;
}
```
# Complexity
## Time Complexity:O(n+k), 
where n is the length of the string, and k=26 is the size of the alphabet.
Counting takes O(n), reconstruction takes O(k).

## Space Complexity:O(k) 
for the frequency array, where k=26.

# Solution (2nd)
```C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str;
    cin>>str;
    sort(str.begin() , str.end());
    cout<<str<<endl;

    return 0;
}
```
# Complexity :
Time Complexity: O(n log n).

Space Complexity: O(n) (auxiliary space for sorting).

