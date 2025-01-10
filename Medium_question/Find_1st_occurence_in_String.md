# “Given two strings text and pattern find the first occurrence of str1 in str2 if found print it’s index if not found print -1.”

Examples:

Example 1:
## Input: 
```str1 = "takeuforward"```
```str2 = “forward”```
## Output: 5

Explanation: "Forward" is present in the 5th index in "takeuforward"

Example 2:
## Input: 
```str1 = “hello”```
```str2 = “az”```
## Output: -1

Explanation: "az" is not a substring of "hello"

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
int FirstOccurence(string str1 , string str2){
  int n = str1.length();
  int m = str2.length();
  
  if(m > n) return -1;
  for(int i=0 ;i <= n - m;i++){
      int j = 0;
      
      while(j < m && str1[i + j] == str2[j]){
          j++;
      }
      if(j == m){
          return i;
      }
  }
  return -1;
}

int main()
{
    string str1 , str2 ;
    cin>>str1>>str2;
    cout<<FirstOccurence(str1, str2);
    
    return 0;
}
```
# Complexity
## Time Complexity:
Outer loop runs O(n−m+1), and the inner loop runs up to O(m).
Worst-case: O((n−m+1)⋅m).
Simplified: O(n⋅m).

## Space Complexity: O(1), as no additional space is used.