# Find Reverse Kth charecter
One day, Jack finds a string of characters. He is very keen to arrange them in reverse order, i.e., the first characters become the last characters, the second characters become the second-last characters, and so on.

Now he wants your help  to find the kth character from the new string formed after reverse the original string.

**Note:** String contains only lowercase Latin letters.

***Input Format***

The first line contains two integers n, k — the length of array and the value of k respectively.

The second line contains a string containing n characters.

***Output Format***

Print a single line containing the kth character of the string.

**Constraints**

```1 ≤ k ≤ n≤ 10^6```

### Testcase Input

```plaintext
5 2
abdfa
```
### Testcase Output
```plaintext
f
```

## Solution
```C++
#include <bits/stdc++.h> 
using namespace std;

int main()
{
   int n , k;
   cin>>n>>k;
   
   string str;
   cin>>str;
   
   cout<<str[n-k]<<endl;
    return 0;
}
```
## Complexity Analysis:

**Time Complexity:** ```O(1)``` — Direct access to the n−k index in the string.

**Space Complexity:** ```O(1)``` — No extra space used.