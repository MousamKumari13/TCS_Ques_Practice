# count how many pairs of shoes you can form.
You are given a list of shoes, where each shoe has a size and is either a left shoe or a right shoe. Your task is to count how many pairs of shoes you can form. A valid pair consists of one left shoe and one right shoe of the same size.

Write a program to calculate and print the total number of pairs that can be formed from the given list of shoes.

Input:
An integer N representing the number of shoes in the list.
A list of N strings, where each string represents the size of the shoe, followed by either 'L' (for left shoe) or 'R' (for right shoe) ```(e.g., "10L" or "10R").````
Output:
Return the total number of complete pairs of shoes that can be formed.
Example 1:
## Input:
```6```
```10L 10R 12L 12R 10L 12R```
## Output:
```2```

Explanation:

You can form two pairs:
One pair of size 10: ("10L", "10R")
One pair of size 12: ("12L", "12R")
Example 2:
## Input:
```4```
```8L 8R 10L 10L```
## Output:
```1```

Explanation:

You can form one pair: ("8L", "8R").
The remaining "10L" shoes cannot form a pair as there is no matching "10R".

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

int countPairs(int n ,vector<string>&  arr ){
    
    unordered_map<int ,int> leftshoes;
    unordered_map<int ,int> rightshoes;
    
    for(int i =0 ;i<n ;i++){
        int size = stoi(arr[i].substr(0, arr[i].size() - 1)); 
        char type = arr[i].back();
        
        if(type == 'L'){
            leftshoes[size]++; 
        }else {
              rightshoes[size]++; 
        }
    }
    int pairs =0;
    
    for(auto& pair : leftshoes){
        int size = pair.first;
        if(rightshoes.find(size) != rightshoes.end()){
            pairs += min(pair.second , rightshoes[size]);
        }
    }
    return pairs;
   
 }
int main()
{
    int n;
    cin>>n;
    vector<string> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    
    cout << countPairs(n, arr) << endl;
    return 0;
}
```
# Complexity

Time Complexity:```O(N)```, where N is the number of shoes in the input list. We loop through the list once to count the left and right shoes and then iterate over the keys in the leftShoes map, which is at most N.

Space Complexity :``` O(N)```, as we store counts for each unique shoe size in two hash maps (leftShoes and rightShoes). The number of unique shoe sizes will at most be N.