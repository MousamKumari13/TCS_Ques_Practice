# Find the Number of Two wheeler and Four wheeler vech
An automobile company manufactures both a two wheeler (TW) and a four wheeler (FW). A company manager wants to make the production of both types of vehicle according to the given data below:

1st data, Total number of vehicle (two-wheeler + four-wheeler)=v

2nd data, Total number of wheels = W


The task is to find how many two-wheelers as well as four-wheelers need to manufacture as per the given data.


Example :

# Input :

```200  -> Value of V```

```540   -> Value of W```


# Output :

```TW =130 FW=70```


Explanation:

130+70 = 200 vehicles

(70*4)+(130*2)= 540 wheels


Constraints :

2<=W  W%2=0  V<W


Print “INVALID INPUT” , if inputs did not meet the constraints.

# Solution
``` C++
#include <bits/stdc++.h>
using namespace std;

int main() {
   int V , W;
   cin>>V>>W;
   int TW , FW;
   
   if(2 > W || W % 2 != 0 || V > W){
       cout<<"INVALID INPUT"<<endl;
   }
   
   TW = (4 * V - W)/2;
   FW = V - TW;
   
   cout<<"TW =" <<TW<<" "<<"FW = "<<FW<<endl;
    return 0;
}
```
# Approach
Tw = x
FW = y

Given that 

x + y = V
2x + 4y = w

Solving the equation

y = v - x

putting on it eq 2

2x + 4 ( v- x)= w
2x + 4v -4x = w
-2x + 4v = w

x = (4 * v - w) / 2

TW = ((4 * v - w) / 2)

FW =  v - x
Fw = V - TW

# Complexity
 Time Complexity: O(1)
Space Complexity: O(1)