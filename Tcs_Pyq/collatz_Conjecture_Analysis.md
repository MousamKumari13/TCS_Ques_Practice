# **Collatz Conjecture Analysis**

The program implements a detailed analysis of the **Collatz Conjecture** (also known as the 3n + 1 problem). Based on a given positive integer \( n \), the program performs the following:

---

### **Problem Statement**

1. Given a positive integer \( n \):
   - Generate the **Collatz sequence** starting from \( n \) until it reaches 1.
   - The rules for generating the sequence are as follows:
     - If \( n \) is even: \( n = n / 2 \).
     - If \( n \) is odd: \( n = 3n + 1 \).
   - Continue this process until \( n = 1 \).

2. For all integers from 1 to \( n \), find:
   - The **maximum length of the Collatz sequence** and the starting integer \( k \) that produces this maximum length.
   - The **maximum value** encountered in any Collatz sequence and the starting integer \( k \) that produces this maximum value.

---

### **Input Format**

1. A single string input representing a positive integer \( n \).  
   - If the input is not a positive integer, the program should output `Error!`.

---

### **Output Format**

1. The **Collatz sequence** starting from \( n \).
   - Example: `[n, ..., 1]`.
2. The **maximum sequence length** and the corresponding integer \( k \).
3. The **maximum value** encountered in any sequence and the corresponding integer \( k \).

---

### **Examples**

#### Example 1:
**Input:**
```plaintext
5
```

**Output:**
```plaintext
Sequence: [5, 16, 8, 4, 2, 1]
8 3
16 3
```

#### Explanation:
- The Collatz sequence starting from \( 5 \) is `[5, 16, 8, 4, 2, 1]`.
- The maximum sequence length from 1 to 5 is \( 8 \), starting with \( k = 3 \).
- The maximum value encountered in sequences from 1 to 5 is \( 16 \), starting with \( k = 3 \).

---

#### Example 2:
**Input:**
```plaintext
10
```

**Output:**
```plaintext
Sequence: [10, 5, 16, 8, 4, 2, 1]
20 9
52 9
```

#### Explanation:
- The Collatz sequence starting from \( 10 \) is `[10, 5, 16, 8, 4, 2, 1]`.
- The maximum sequence length from 1 to 10 is \( 20 \), starting with \( k = 9 \).
- The maximum value encountered in sequences from 1 to 10 is \( 52 \), starting with \( k = 9 \).

---

### **Constraints**
1. \( n \) must be a positive integer.
2. If \( n \) is invalid, output `Error!`.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

// Function to calculate the Collatz sequence length and maximum value for a given number
pair<int, int> collatzAnalysis(int n) {
    int length = 1; // The sequence always includes the number itself
    int maxValue = n; // Maximum value encountered in the sequence
    
    while (n != 1) {
        if (n % 2 == 0) {
            n /= 2;
        } else {
            n = 3 * n + 1;
        }
        maxValue = max(maxValue, n); // Update maximum value
        length++; // Increment sequence length
    }
    return {length, maxValue};
}

void collatzConjectureAnalysis(int n) {
    if (n <= 0) {
        cout << "Error!" << endl;
        return;
    }

    // Print the Collatz sequence for the given number
    cout << "Sequence :";
    int temp = n;
    while (temp != 1) {
        cout << temp << " ";
        if (temp % 2 == 0) {
            temp /= 2;
        } else {
            temp = 3 * temp + 1;
        }
    }
    cout << "1" << endl;

    // Variables to track the maximum length and value
    int maxLength = 0, maxLengthNum = 0;
    int maxVal = 0, maxValNum = 0;

    for (int i = 1; i <= n; i++) {
      pair<int, int> result = collatzAnalysis(i);
      int length = result.first;
       int maxValue = result.second;
        
        // Update maximum length and the number that produces it
        if (length > maxLength) {
            maxLength = length;
            maxLengthNum = i;
        }

        // Update maximum value and the number that produces it
        if (maxValue > maxVal) {
            maxVal = maxValue;
            maxValNum = i;
        }
    }
    cout << maxLength << " " << maxLengthNum << endl;
    cout << maxVal << " " << maxValNum << endl;
}

int main() {
     int n;
     cin>>n;

    collatzConjectureAnalysis(n);

    return 0;
}
```

## Complexity

Time Complexity: O(nlogn)


Space Complexity: O(nlogn)
