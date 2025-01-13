# You are given an array of strings where each string represents an integer. Your task is to find the maximum difference between any two elements in the array, where the larger element appears later in the list.

In other words, you need to find the largest possible difference arr[j] - arr[i] such that j > i and the integer value of arr[j] > arr[i]. If no such pair exists, return INT_MIN.   Input:
A vector arr of strings, where each string represents an integer.
Output:
Return the maximum difference between two elements such that the larger element appears after the smaller element. If no such pair exists, return INT_MIN.Example 1:
## Input:
```vector<string> arr = {"-3", "-5", "1", "6", "-7", "8", "11"};```
## Output:
```18```

Explanation:
The maximum difference is 11 - (-7) = 18.

Example 2:
## Input:
```vector<string> arr = {"-5", "-6", "-7", "-8"};```
## Output:
```INT_MIN```

Explanation:
Since all numbers are negative and no larger number appears after a smaller number, the result is INT_MIN.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
int maxDiff(vector<string>&  arr ){
    int n = arr.size();
    int minele = INT_MAX;
    int maxele = INT_MIN;
    for (int i = 0; i < n; ++i) {
        int num = stoi(arr[i]);

        if (num > minele) {
            maxele = max(maxele, num - minele);
        }

        minele= min(minele, num);
    }

    return maxele; 
 }
int main()
{
    int n;
    cin>>n;
    vector<string> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
   
   int result = maxDiff(arr);

    if (result == INT_MIN) {
        cout << "INT_MIN" << endl;
    } else {
        cout << result << endl;
    }
    return 0;
}
```
# Complexity
 Time Complexity:```O(n)```We loop through the array once to calculate the maximum difference.
Space Complexity:```O(1)```: We only use a few extra variables (min_so_far and max_diff), so the space complexity is constant.