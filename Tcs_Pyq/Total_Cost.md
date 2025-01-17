# Calculate Shipping Cost

## Problem Statement:

A shipping company calculates the cost of delivery based on the weight of the package and the distance it needs to travel. The cost is calculated as follows:

1. A base cost of $5.00 is applied to all shipments.
2. The cost for the weight of the package is $2.00 per kilogram.
3. The cost for the distance is $0.50 for every 10 kilometers (rounded down to the nearest multiple of 10).

Write a program to calculate the total shipping cost given the weight of the package and the distance to be traveled.

## Input:
- An integer representing the weight of the package (in kilograms).
- An integer representing the distance to be traveled (in kilometers).

## Output:
- Print the total shipping cost formatted to two decimal places, prefixed with a dollar sign ($).

## Example:

### Input:

10
250


### Output:

$37.50


### Explanation:
- Base cost: $5.00  
- Weight cost: \(10 \times 2.00 = 20.00\)  
- Distance cost: \((250 / 10) \times 0.50 = 12.50\)  
- Total cost: \(5.00 + 20.00 + 12.50 = 37.50\)

## Constraints:
- The weight of the package will be between 1 and 1000 kilograms.
- The distance will be between 1 and 10,000 kilometers.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

void Cost(int weight, int dis){
   double baseCost = 5.00;
   double weightCost = weight * 2.00;
   double distance_cost = (dis / 10)* 0.50;
   
   double totalCost = baseCost + weightCost + distance_cost;
   
   cout<<"$"<< fixed << setprecision(2) <<totalCost<<endl;
   
}

int main() {
    int weight , dis;
    cin >>weight >> dis;

    Cost(weight , dis);
    return 0;
}
```

# Complexity
**Time Complexity**:``` O(1)```

**Space Complexity:** ```O(1)```






