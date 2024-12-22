# Print the positive integer value after toggling all bits”.

Joseph is learning digital logic subject which will be for his next semester. He usually tries to solve unit assignment problems before the lecture. Today he got one tricky question. The problem statement is “A positive integer has been given as an input. Convert decimal value to binary representation. Toggle all bits of it after the most significant bit including the most significant bit. Print the positive integer value after toggling all bits”.

Constraints :
```1<=N<=100```
Example 1:

# Input :

```10  -> Integer```

# Output :

```5    -> result- Integer```


Explanation:

Binary representation of 10 is 1010. After toggling the bits(1010), will get 0101 which represents “5”. Hence output will print “5”.

# Solution 

```C++
#include <bits/stdc++.h>
using namespace std;
int toggleBits(int n){
    if(n ==0) return 1;
    
    int sol = 0;
    int nxtbit = 1;
    
    while(n != 0){
        int lastbit = (n & 1);
        if(lastbit == 0){
            sol |= nxtbit;
        }
        nxtbit <<= 1;
        n >>=1;
    }
    return sol;
}
int main() {
   int n;
   cin>>n;
   
   cout<<toggleBits(n)<<endl;
    return 0;
}
```
# For understanding Approach watch this vid -> 
https://youtu.be/gxRB6DOQDOQ?si=oml9JIGOmaCLYxnT

# Complexity
Time complexity: O(log n)

Space complexity: O(1)

# 2nd Approach 

```C++
#include <bits/stdc++.h>
using namespace std;
int toggleBits(int n){
    if(n ==0) return 1;
    
   int numbits = floor(log2(n)) + 1;
   int mask = (1 << numbits) -1 ;
   
   return n ^ mask;
}
int main() {
   int n;
   cin>>n;
   
   cout<<toggleBits(n)<<endl;
    return 0;
}
```
# Complexity 
Time complexity: O(1)

Space complexity: O(1)

# Explanation

The function toggles all bits of the integer n (i.e., it flips every 0 to 1 and every 1 to 0 in the binary representation of n).

1. numbits = floor(log2(n)) + 1:

This calculates the number of bits needed to represent the number n in binary. For example, if ```n = 5```, the binary representation is ```101```, which requires ```3``` bits, so numbits will be ```3```.

2. mask = (1 << numbits) - 1:

This creates a mask with all numbits set to 1. For example, if ```numbits = 3```, the mask will be ```111``` (binary), which is equal to ```7```` in decimal. This mask will have 1s in all the positions where the original number has bits, allowing us to toggle the bits.

3. n ^ mask:

The XOR operation flips all the bits of n where the mask has 1 bits. For example, if ```n = 5``` (binary 101) and the mask is ```7 (binary 111)```, the result of ```n ^ mask``` will be ```2 (binary 010)```, flipping all the bits of n.