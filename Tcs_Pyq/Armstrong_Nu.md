# Armstrong Number Checker

*Problem Statement:*

Write a program to check if a given number is an Armstrong number. An Armstrong number (also known as a narcissistic number) is a number that is equal to the sum of its own digits each raised to the power of the number of digits. 

For example, 153 is an Armstrong number because:

\[
1^3 + 5^3 + 3^3 = 153
\]
---

## Task:

- The program should take a list of comma-separated numbers as input.
- For each number in the list, check if it's an Armstrong number.
- If any Armstrong numbers are found, display them. If no Armstrong numbers are found, display "No Armstrong numbers present".

---

## Input:
- A string of comma-separated numbers. 
  Example: 
  
  ```153,370,371,407,10```
  

## Output:
- If Armstrong numbers are found, print them. 
- If no Armstrong numbers are present, print: "No Armstrong numbers present".

Example:

### Input:
```plaintext
153,370,371,407,10
```

### Output:
```plaintext
153 370 371 407
```

## Constraints:
- You may assume that the input will contain valid integers.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
bool Num(int num){
    int temp = num;
    int ans =0;
    int dig =0 ;
    
    while(temp >0){
        temp /= 10;
          dig++;
    }
   
   temp = num;
   
    while(temp > 0){
        
        int digit = temp % 10;
        ans += pow(digit , dig);
        temp /= 10;
    }
    return  num == ans;
}

void armstrong(int n , vector<int>& arr ){
    vector<int> ans;

    for(int i = 0 ;i < n ;i++){
        if(Num(arr[i])){
            ans.push_back(arr[i]);
        }
    }
    if(ans.empty()){
        cout<<"No armstrong Number present" << endl;
    }else{
        for(int i=0 ;i< ans.size() ; i++){
           cout<<arr[i]<<" ";
        }
    }
  
}
int main()
{
    int n;
    cin>>n;
    
    vector<int> arr(n);
    
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    armstrong(n , arr);
    return 0;
}
```

# Complexity

**Time Complexity:**

  - Checking if a number is Armstrong: O(d), where d is the number of digits.
  - For n numbers with average d digits: **O(n⋅d).**\


**Space Complexity:**
  - **O(n)** for storing the armstrongNumbers vector.