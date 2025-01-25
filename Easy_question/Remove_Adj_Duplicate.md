# Remove Consecutive Duplicates

Problem statement
You are given a string ‘str’ of size ‘N’. Your task is to remove consecutive duplicates from this string recursively.

### For example:

If the input string is ‘str’ = ”aazbbby”, then your output will be “azby”.
Note that we are just removing adjacent duplicates.
Detailed explanation ( Input/output format, Notes, Images )
## Sample Input 1:
```plaintext
2
7
aazbbby
6
aabbcb
```
## Sample Output 1:
```plaintext
azby
abcb
```
Explanation of Sample Input 1:
Test Case 1:

Given ‘str' = ”aazbbby”
After removing adjacent duplicates string will be “azby”

Test Case 2:

Given ‘str’ = “aabbcb”
After removing adjacent duplicates string will be “abcb”
## Sample Input 2:
```plaintext
2
5
abcde
5
aaaaa
```
## Sample Output 2:
```plaintext
abcde
a
```
Explanation of Sample Input 2:
Test Case 1:

Given ‘str' = ”abcde”
There are no duplicates in the input string so the final string will be “abcde” 

Test Case 2:

Given ‘str’ = “aaaaa”
After removing adjacent duplicates string will be “a”

## Problem link->
https://www.naukri.com/code360/problems/remove-consecutive-duplicates_893195?topList=tcs-interview-questions&problemListRedirection=true&leftPanelTabValue=PROBLEM&count=25&page=1&search=&sort_entity=order&sort_order=ASC&customSource=studio_nav

# Solution
```
#include <bits/stdc++.h>
using namespace std;

string removeDuplicate(string &s) {
    int n = s.length();
    string res = "";

    for (int i = 0; i < n; i++) {
        // Only add the current character if it's different from the next character
        if (i == n - 1 || s[i] != s[i + 1]) {
            res.push_back(s[i]);
        }
    }
    return res;
}

int main() {
    string s;
    cin >> s;

    string result = removeDuplicate(s);
    cout << result << endl;

    return 0;
}
```
## Overall Complexity:

**Time Complexity:**O(n), where n is the length of the string.

**Space Complexity:** O(n) for the res string to store the result.