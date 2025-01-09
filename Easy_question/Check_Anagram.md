# check if two strings are anagrams of each other or not.
Problem Statement: Given two strings, check if two strings are anagrams of each other or not.

Examples:

Example 1:
## Input: ```CAT, ACT```
## Output: ```true```
Explanation: Since the count of every letter of both strings are equal.

Example 2:
## Input: ```RULES, LESRT ```
## Output: ```false```
Explanation: Since the count of U and T  is not equal in both strings.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

bool areAnagrams(string str1 , string str2){
    if (str1.length() != str2.length())
        return false;
        
    map<char, int> mp1 ,mp2;
  
    for(char ch : str1){
        mp1[ch]++;
    }
    for(char ch : str2){
        mp2[ch]++;
    }
   
    return mp1 == mp2;
    
}
int main()
{
   string str1 , str2;
   cin>>str1>>str2;
   
    if (areAnagrams(str1, str2)) {
        cout << "True"<<endl;
    } else {
        cout << "False"<<endl;
    }
    return 0;
}
```
# Complexity

Using Frequency Map:
Time Complexity: n is the length of the strings.
Space Complexity: O(1) (Fixed alphabet size).

Using Sorting:
Time Complexity: O(nlogn), due to sorting.
Space Complexity: O(1) (In-place sorting).