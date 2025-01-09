# Write a C++ program that performs the following tasks:
1. Reads the number of items (n) purchased.
2. For each item, inputs:
 - The item's name (string).
 - Quantity of the item (integer).
 - Price per unit (integer).
3. Calculates:
 - The total cost of all items purchased.
 - The name of the item with the highest cost (calculated as quantity * price).
 - The average cost of the items.
Note: Ensure the average cost is displayed up to 2 decimal places.
Input:
- The first line contains an integer n (number of items).
- The next n lines contain the name of the item (string), its quantity (integer), and its price per unit(integer).
Output:
- The name of the item with the highest cost.
- The total cost of all items.
- The average cost of the items (formatted to 2 decimal places).
Example: 
## Input:
```3```
```Apples 10 50```
```Oranges 5 40```
```Bananas 8 30```
## Output:
```Task 1 - Item: Apples```
```Total price: 940.00```
```Average Price: 313.33```

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n ;
    cin>>n;
    string itemname , highestCostItm ;
    int quantity ,price , totalCost =0 , maxCost = 0;
    double avgCost ;
    
    vector<int> itemCosts;
    for(int i =0 ;i<n ;i++){
        cin>>itemname>>quantity>>price;
        
        int itemCost = quantity * price;
        totalCost += itemCost;
        itemCosts.push_back(itemCost);
        
        if(itemCost > maxCost){
            maxCost = itemCost;
            highestCostItm = itemname;
        }
    }
    avgCost = totalCost/n;
    
    cout<<"Item Name :"<<highestCostItm<<endl;
    cout<<"Total Cost :"<<totalCost<<endl;
    cout<<"Average Cost :"<<fixed << setprecision(2) <<avgCost<<endl;
    return 0;
}
```
# Complexity
Time Complexity: O(n) (for reading and calculations).
Space Complexity: O(n) (to store item costs).





