# Replace zero by One
Problem Statement: You are given an integer. Your task is to replace all the zeros in the integer with ones.

Examples:

Example 1:
## Input: 
```N = 102003```
## Output: 
```112113```
Explanation: The 2nd,4th and 5th position from left contain 0.The resultant integer has replaced the 0’s in those  positions with 1.

Example 2:
## Input:  
```204```
## Output: 
```214```
Explanation: The 2nd position from left contain 0. The resultant integer has replaced the 0 in that position with 1.

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void removeZeroByOne(string str){
    int n = str.length();
    string result = "";
    for(int ch : str){
        if(ch == '0'){
            result += '1';
        }else{
            result += ch;
        }
    }
   cout<<result;
}
int main()
{
   string str;
   cin>>str;
   removeZeroByOne(str);
    return 0;
}
```
# Complexity:
Time Complexity: Still O(n) since we iterate through the string once.
Space Complexity: Still O(n) for storing the result.

# 2nd Solution 
```c++

#include <bits/stdc++.h>
using namespace std;
void removeZeroByOne(int n){
    int result = 0 , place = 1;
  while(n > 0){
      int dig = n %10;
      if(dig == 0){
          dig = 1;
      }
      result += dig * place;
      place *= 10;
      n /= 10;
  } 
  cout<<result;
  
}
int main()
{
   int num;
   cin>>num;
   removeZeroByOne(num);
    return 0;
}
```
# Complexity:
Time Complexity: Still O(n) since we iterate through the string once.
Space Complexity: Still O(n) for storing the result.