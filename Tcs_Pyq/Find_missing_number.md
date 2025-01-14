# Find the Missing Number in a Sequence (String Input Format)

Write a program to find the missing number from a sequence of integers ranging from 1 to N+1. The input numbers will be provided as a space-separated list of integers in string format.

Input:

The first line contains an integer N, representing the size of the array (excluding the missing number).
The second line contains a space-separated list of N integers as strings.
Output: Print the missing number from the sequence.

Constraints:

The array contains integers from 1 to N+1 with one number missing.
The integers are provided as strings.
The program should convert the strings to integers efficiently.
Example 1:

## Input:
```4```
```"1" "2" "4" "5"```
## Output:
```Missing number: 3```

Explanation:
The full sequence should be [1, 2, 3, 4, 5].
The missing number is 3.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void missingNumber(vector<string>& arr){
    int n = arr.size();
    int sum = (n+1)*(n+2)/2;
    
    int originalSum = 0;
    for(int i =0 ;i<n ;i++){
        int num = stoi(arr[i]);
        originalSum += num;
    }
    
    cout<<"Missing number: "<<sum - originalSum<<endl;
}
int main()
{
   int n ;
   cin>>n;
   vector<string> arr(n);
   
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   missingNumber(arr);
    return 0;
}
```

# Complexity
Time Complexity: O(n)


Space Complexity: O(n)
