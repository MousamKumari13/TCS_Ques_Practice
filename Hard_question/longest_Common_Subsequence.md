 
 # Longest Common Subsequence

***Problem statement***
Given two strings, 'S' and 'T' with lengths 'M' and 'N', find the length of the 'Longest Common Subsequence'.

For a string 'str'(per se) of length K, the subsequences are the strings containing characters in the same relative order as they are present in 'str,' but not necessarily contiguous. Subsequences contain all the strings of length varying from 0 to K.

Example :
Subsequences of string "abc" are:  ""(empty string), a, b, c, ab, bc, ac, abc.
Detailed explanation ( Input/output format, Notes, Images )
**Constraints :**
```plaintext
0 <= M <= 10 ^ 3
0 <= N <= 10 ^ 3
```

Time Limit: 1 sec

## Sample Input 1 :
```plaintext
adebc
dcadb
```
## Sample Output 1 :
```plaintext
3
```

Explanation of the Sample Output 1 :
Both the strings contain a common subsequence 'adb', which is the longest common subsequence with length 3. 


## Sample Input 2 :
```plaintext
ab
defg
```
## Sample Output 2 :
```plaintext
0
```
Explanation of the Sample Output 2 :
The only subsequence that is common to both the given strings is an empty string("") of length 0.

## Problem link->
**leetcode** -> https://leetcode.com/problems/longest-increasing-subsequence/description/
**Geeksforgeeks** -> https://www.geeksforgeeks.org/problems/longest-common-subsequence-1587115620/1
**CodingNinjas** -> https://www.naukri.com/code360/problems/longest-common-subsequence_624879?interviewProblemRedirection=true&search=&count=25&page=1&sort_entity=order&sort_order=ASC&leftPanelTabValue=PROBLEM&customSource=studio_nav

## Explanation video link->
https://youtu.be/aJNu_DLyOxY?si=3Ak7qo7DmpRFBSB7

# Solution
```C++
#include <bits/stdc++.h> 
using namespace std;
int m , n;
int T[1001][1001];

int solve(string& s , string& t, int i , int j){
    if(i >= m || j >= n){
        return 0;
    }
    
    if(T[i][j] != -1){
        return T[i][j];
    }
    
    if(s[i] == t[j]){
        return T[i][j] = 1 + solve(s , t , i+1 , j+1);
    }
    
    return T[i][j] = max(solve(s , t , i+1 , j) , solve(s , t , i , j+1));
}
int longestCommonSubsequence(string& s , string& t){
    m = s.length();
    n = t.length();
    
    memset(T , -1 , sizeof(T));
    return solve(s , t , 0 ,0);
}

int main()
{
   string s , t;
   cin>>s>>t;
   
   cout<< longestCommonSubsequence(s,t);
    return 0;
}
```
## Complexity

**Time Complexity:**
The time complexity of the solution is ```O(m × n),``` where:

m is the length of the first string (s1), and
n is the length of the second string (s2).
This is because the recursive solve function fills a 2D DP table (t) of size m × n, and each cell is computed only once.

**Space Complexity:**
The space complexity is:

```O(m × n)``` for the 2D DP table (t).
O(m + n) for the recursion stack in the worst case (due to the depth of the recursive calls).
***Total space complexity*** = ```O(m × n)``` (dominant factor).








