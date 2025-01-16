# Problem Statement

You are given a list of strings (e.g., fruit names) as input. Your task is to:

1. Count the frequency of each unique string in the list.
2. Print the unique strings in sorted order.
3. Print the unique strings in reverse sorted order.

## Input
A single line consisting of space-separated strings (e.g., names of fruits).

### Example:
```plaintext
apple banana apple orange banana apple
```

## Output
1. First, print the unique strings in sorted order (alphabetically).
2. Then, print the unique strings in reverse sorted order.

### Example Output:
```plaintext
apple banana orange
orange banana apple
```

## Constraints
- The input will contain at most 1000 strings.
- Each string will be composed of alphabetic characters.

## Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void sortByFreq(int n , vector<string>& fruits){
    unordered_map<string , int> freq;
    
    for(auto fruit : fruits){
        freq[fruit]++;
    }
    
    vector<pair<int , string>> sortedfruit;
    for(auto& entry : freq){
        sortedfruit.push_back({entry.second , entry.first});
    }
    
    // Sort by frequency (in ascending order)
    sort(sortedfruit.begin() , sortedfruit.end() , [](const pair<int , string>& a , const pair<int , string>& b){
        return a.first > b.first;
    });
    
    for(auto & entry : sortedfruit){
        cout<<entry.second<<" ";
    }
    
    cout<<endl;
    
    // Print the sorted fruits based on frequency (reverse order)
    sort(sortedfruit.begin() , sortedfruit.end() , [](const pair<int , string>& a , const pair<int, string>& b){
        return a.first< b.first;
    });
    
    for(auto & entry : sortedfruit){
        cout<<entry.second<<" ";
    }
    
    
}
int main()
{
    int n;
    cin>>n;
    vector<string> fruit(n);
    for(int i=0 ;i< n ;i++){
        cin>>fruit[i];
    }
    sortByFreq(n , fruit);
    return 0;
}
```

### Complexity
***Time Complexity:***

 - Counting frequencies: O(n), where n is the number of fruits.
 - Sorting the vector: O(u log u), where u is the number of unique fruits.
 - Overall time complexity is **O(n + u log u).**


***Space Complexity:***

 - Storing frequencies: O(u), where u is the number of unique fruits.
 - Storing the sorted vector: O(u).
 - Overall space complexity is **O(u + n)**.