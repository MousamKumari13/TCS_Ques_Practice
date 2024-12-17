# Armstrong Number
Problem Statement: Given an integer N, return true it is an Armstrong number otherwise return false.

An Amrstrong number is a number that is equal to the sum of its own digits each raised to the power of the number of digits.

Examples
Example 1:
# Input:
```N = 153```

# Output: ```True```
Explanation: 13+53+33 = 1 + 125 + 27 = 153
Example 2:
# Input:
```N = 371```
# Output: True
Explanation: 33+53+13 = 27 + 343 + 1 = 371

# problem Link ->
https://www.naukri.com/code360/problems/check-armstrong_589?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf

# Solution
``` C++
#include <bits/stdc++.h>
using namespace std;
bool Armstrong(int num){
    int orignum = num;
    int countdig =0;
    int armno = 0;
    int temp = num;
    while(temp >0){
        temp /=10;
        countdig++;
    }
    
    temp = num;
    while(temp >0){
        int rem = temp % 10;
        armno += pow(rem , countdig);
        temp /=10;
    }
    
    return orignum == armno;
}
int main() {
  int n;
  cin>>n;
  
  if(Armstrong(n)){
      cout<<"True"<<endl;
  }else{
      cout<<"False"<<endl;
  }
    return 0;
}
```
# Complexity
Time complexity: O(d) or O(log n), where d is the number of digits in n.
Space complexity: O(1) (constant space).
