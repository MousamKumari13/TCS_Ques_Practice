# Sum of Unique Elements

## Problem Statement:

You are given a list of integers as input. Your task is to calculate the sum of all integers that appear exactly once in the list.

Write a program to implement the solution.

### Input:
A single line of space-separated integers.

### Output:
Print the sum of all integers that appear exactly once.

### Example:

#### Input:

4 5 6 4 7 8 5 9


#### Output:

30


### Explanation:
In the input, the numbers that appear exactly once are 6, 7, 8, 9. Their sum is 6 + 7 + 8 + 9 = 30.

### Constraints:
- The list can contain up to \(10^5\) integers.
- Each integer in the list will be between \(-10^6\) and \(10^6\).

# SOlution
```C++
#include <bits/stdc++.h>
using namespace std;

int SumOfUniqueEle(int n , vector<int>& arr){
    int sum = 0;
    unordered_map<int, int> freq;

    // Count the frequency of each element
    for (int num : arr) {
        freq[num]++;
    }

    // Add elements with frequency 1 to the sum
    for (auto& ele : freq) {
        if (ele.second == 1) {
            sum += ele.first;
        }
    }

    return sum;
}

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);

    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
     cout<<SumOfUniqueEle(n , arr);
    return 0;
}
```

## Complexity
**Time Complexity:** ```O(n)```

**Space Complexity:** ```O(n)``` (for the hash table).
