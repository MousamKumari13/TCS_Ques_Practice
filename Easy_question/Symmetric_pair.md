# find all the symmetric pairs
Problem Statement: Given an array of pairs, find all the symmetric pairs in the array.

Examples:

Example 1:
# Input: 
```(1,2),(2,1),(3,4),(4,5),(5,4)```
# Output: 
```(2,1) (5,4)```

Explanation: Since (1,2) and (2,1) are symmetric pairs and (4,5) and (5,4) are symmetric pairs.

Example 2:
# Input:
```(1,5),(2,3),(4,2),(5,1),(2,4)```
# Output: 
```(2,4) (5,1)```

Explanation: Since (1,5) and (2,4) are symmetric pairs and (5,1) and (4,2) are symmetric pairs.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void findSymmetric(vector<pair<int , int>>& pairs){
    unordered_map<int , int> mp;
    
    vector<pair<int ,int>> result;
    
    for(auto & p: pairs){
        int first = p.first;
        int second = p.second;
        
        if(mp.find(second) != mp.end() && mp[second] == first){
            result.push_back({second , first});
        }else{
            mp[first] = second;
        }
    }
    
    for(auto &p : result){
        cout << "(" << p.first << "," << p.second << ") ";
    }
    cout<<endl;
}
int main() {
   int n;
   cin>>n;
   
   vector<pair<int , int>> pairs;
   
   for(int i =0 ; i< n ;i++){
       int a , b;
       cin>>a>>b;
       pairs.push_back({a , b});
   }
   findSymmetric(pairs);
    return 0;
}
```
# Complexity
Time Complexity:O(n)
Space Complexity:O(n)