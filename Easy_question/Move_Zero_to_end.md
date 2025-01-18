## Move zero to End.

A chocolate factory is packing chocolates into packets. The chocolate packets are represented by an array arr of *N* integer values. The task is to find the empty packets (0) of chocolate and push them to the end of the conveyor belt (array), maintaining the order of the non-empty packets.

---

### Input Format:
1. *N*: The number of packets (integer).
2. *arr*: The array containing N integer values, where 0 represents an empty packet.

---

### Output Format:
The reordered array where all the empty packets (0) are moved to the end, while maintaining the order of non-empty packets.

---

### Example 1:
#### Input:

7       # Value of N
[4,5,0,1,9,0,5,0]  # Elements of arr[0] to arr[N-1]

#### Output:

4 5 1 9 5 0 0 0

#### Explanation:
The array has 3 empty packets represented as 0. These 0`s are moved to the end of the array, and the order of the non-empty packets (`4, 5, 1, 9, 5) is maintained.

---

### Example 2:
#### Input:

6       # Value of N
[6,0,1,8,0,2]  # Elements of arr[0] to arr[N-1]

#### Output:

6 1 8 2 0 0

#### Explanation:
The array has 2 empty packets represented as 0. These 0`s are moved to the end of the array, and the order of the non-empty packets (`6, 1, 8, 2) is maintained.

---

### Constraints:
1. \( 1 \leq N \leq 10^5 \)
2. \( -10^9 \leq arr[i] \leq 10^9 \)

---

### Implementation:
This problem can be solved in multiple programming languages like *C++, **Python, or **Java*. Here's the approach:

1. Traverse the array and collect all the non-zero elements.
2. Count the number of zeros.
3. Append zeros to the end of the collected non-zero elements.

---

# Solution
``` C++
#include <bits/stdc++.h>
using namespace std;

void moveZerosToEnd(int N, vector<int>& arr) {
    // Initialize a pointer for the position of the next non-zero element
    int j = 0;

    for (int i = 0; i < N; i++) {
        if (arr[i] != 0) {
            arr[j] = arr[i];
            j++;
        }
    }

    // Fill the remaining elements with zeros
    for (int k = j; k < N; k++) {
        arr[k] = 0;
    }
}

int main() {
    // Input
    int N;
    cin >> N;
    vector<int> arr(N);
    for (int i = 0; i < N; i++) {
        cin >> arr[i];
    }

    // Function call
    moveZerosToEnd(N, arr);

    // Output
    for (int i = 0; i < N; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

# Time and Space Complexity:
**Time Complexity:** ```O(N)``` – Single traversal to reorder the array.


**Space Complexity:** ```O(1)``` – No additional space is used; the operations are performed in-place.
