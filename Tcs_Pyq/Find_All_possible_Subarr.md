# Subarrays Printer

*Problem Statement:*

You are given a list of integers along with the size n as input. The goal is to print all possible subarrays of the list, where each subarray consists of consecutive elements. The subarrays should be printed in the following format:

- Each subarray should be printed on the same line, separated by commas.
- Elements of a subarray should be separated by a space.
- Each subarray should be printed only once.
---

## Input:

- A single line consisting of n followed by a list of n integers.
  - n: The size of the list (integer).
  - A space-separated list of integers follows.

  Example:
  ```plaintext
  4 1 2 3 4
  ```

## Output:

- A single line of subarrays, where each subarray is printed with its elements separated by spaces and the subarrays are separated by commas.

  Example:
  ```plaintext
  1,1 2,1 2 3,1 2 3 4,2,2 3,2 3 4,3,3 4,4
  ```

## Constraints:

- n will be between 1 and 100.
- The integers in the list will be between -1000 and 1000.

## Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void subarray(int n , vector<int>& arr){
    vector<string> ans ;
  
    for(int i =0 ;i<n ;i++){
        string subarray = "";
        for(int j = i ; j<n ;j++){
            
          if(!subarray.empty()){
              
              subarray += " ";
          }
          
          subarray += to_string(arr[j]);
          ans.push_back(subarray);
        }
    }
    
    for(int i=0 ;i<ans.size() ;i++){
        if(i != 0){
            cout<<",";
        }
        cout<<ans[i];
    }
    cout<<endl;
    
}
int main()
{
    int  n;
    cin>> n;
    
  vector<int> arr(n);
    for(int i =0 ;i<n ;i++){
        cin>>arr[i];
    }
    
    subarray(n , arr);
    return 0;
}
```

### Complexity

**Time complexity**:  O(n^2).

**Space complexity**:  O(n^2). because the ans vector stores all possible subarrays, which requires space proportional to the number of subarrays, which is n * (n+1) / 2 = O(n^2).

## Optimize Code 
```C++
#include <bits/stdc++.h>
using namespace std;

void subarray(int n, vector<int>& arr) {
    bool first = true;
    
    // Generate and print subarrays on the go
    for (int i = 0; i < n; i++) {
        string subarr = "";
        for (int j = i; j < n; j++) {
            if (j > i) {
                subarr += " ";
            }
            subarr += to_string(arr[j]);
            
            // Output the subarray immediately
            if (!first) {
                cout << ",";
            }
            cout << subarr;
            first = false;
        }
    }
    cout << endl;
}

int main() {
    int n;
    cin >> n;
    
    vector<int> arr(n);
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    
    subarray(n, arr);
    return 0;
}
```
## Time Complexity: **O(n^2)**
  (still, because we need to print all subarrays).


## Space Complexity: **O(1)**
 (no extra space used for storing subarrays except the input array).