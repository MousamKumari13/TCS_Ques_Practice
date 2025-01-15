# Write a program to process an array of integers input in a specific format and replace elements based on divisibility rules:

---

 - Replace numbers divisible by ```3``` with the string "Three".
 - Replace numbers divisible by ```5``` with the string "Five".
 - Replace numbers divisible by both ```3``` and ```5``` with the string "ThreeFive".

---

Print other numbers as they are.
**Input Format:**
- The first line contains an integer ```n```, the size of the array.
- The second line contains an array of n integers enclosed in square brackets, with space-separated elements.
**Output Format:**
- Print the modified array as a space-separated string.

---

### Constraints:
```plaintext
1≤n≤1000
−10 ^6 ≤Array Elements≤10^6
```
 --- 

## Example Input 1:
```plaintext
5
[3 10 15 7 9]
```

## Example Output 1:
```plaintext
Three Five ThreeFive 7 Three
```

---

## Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void replace(vector<int>& arr){
   int n = arr.size();
   vector<string> ans;
   for(int i =0 ;i<n ;i++){
       if(arr[i]% 3 == 0 && arr[i] % 5 == 0){
           ans.push_back("ThreeFive");
       }else if(arr[i] % 3 == 0 && arr[i] % 5 != 0){
           ans.push_back("Three");
       }else if(arr[i] % 5 == 0 ){
           ans.push_back("Five");
       }else {
           ans.push_back(to_string(arr[i]));
       }
   }
   for(int i =0 ;i< ans.size();i++){
       cout<<ans[i]<<" ";
   }
}
int main()
{
    int n ;
    cin>>n;
    vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    replace(arr);
    return 0;
}
```
## Complexity

**Time complexity :**
- Outer Loop (Processing the array): O(n), where n is the size of the array.
- Each element is checked for divisibility by 3 and 5, which is O(1) per element.
 Overall: Time Complexity = **O(n)**

**Space complexity :**  
- Output Vector (ans): Stores up to n strings.
- Other Variables: Constant space for intermediate variables.
- Overall: Space Complexity = **O(n)**
