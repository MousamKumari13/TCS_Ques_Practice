# check if the string is palindrome or not.
Problem Statement: "Given a string, check if the string is palindrome or not."  A string is said to be palindrome if the reverse of the string is the same as the string.

Examples:

Example 1:
# Input: 
```Str =  “ABCDCBA”```
# Output: 
```Palindrome```

Explanation: String when reversed is the same as string.

Example 2:
# Input:
``` Str = “TAKE U FORWARD”```
# Output: 
```Not Palindrome```

Explanation: String when reversed is not the same as string.

# Solution
```C++

#include<bits/stdc++.h>
using namespace std;
int main() {
    string s;
    cin>>s;
	int n = s.length();
	string origstr = s;
	reverse(s.begin(), s.end());
	if(origstr == s){
	    cout<<"Palindrome"<<endl;
	}else{
	    cout<<"NOt Palindrome"<<endl;
	}
   return 0;
}
```
# Complexity
Time Complexity: O(n)

Space Complexity: O(n)  The program creates an additional string origstr to store the original input, which takes O(n) space.


# 2nd Approach
```C++

#include<bits/stdc++.h>
using namespace std;
bool stringPalindrome(string & str){
    int start = 0 ;
    int end = str.length()-1;
    
    while(start < end){
        if(str[start] != str[end]){
            return false;
        }
        start++;
        end--;
    }
    return true;
}
int main() {
    string s;
    cin>>s;
	
	if(stringPalindrome(s)){
	    cout<<"Palindrome"<<endl;
	}else{
	    cout<<"Not Palindrome"<<endl;
	}

   return 0;
}
```
# Complexity
Time Complexity: O(n)  , We traverse the string once with two pointers.

Space Complexity: O(1)