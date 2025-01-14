# Sort an Array of Characters Based on Custom Order

Write a program to sort an array of characters containing only '3', '6', and '7' based on the following custom order:

All '3's should come first.
All '6's should come next.
All '7's should come last.
The program should sort the array in-place with a single traversal.

Input:

A space-separated list of characters consisting of '3', '6', and '7'.
(The input can have any number of elements, and the program should handle dynamic input.)
Output: Print the sorted array based on the above custom order.

Constraints:

The array will only contain the characters '3', '6', and '7'.
The size of the array is not fixed; it can vary.
The solution should run in O(N) time complexity and use O(1) additional space.
Example 1:

## Input:
```3 6 7 3 6 7 7 3 6```
## Output:
```3 3 3 6 6 6 7 7 7```

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void sortCharAsInt(vector<char>& arr){
    int low =0 , mid =0 , high = arr.size()-1;
    
    while(mid <= high){
        if(arr[mid] == '3'){
            swap(arr[low] , arr[mid]);
            low++;
            mid++;
        }
        else if(arr[mid] == '6'){
            mid++;
        }
        else if(arr[mid] == '7'){
            swap(arr[mid] , arr[high]);
            high--;
        }
    }
    
}
int main()
{
   string input;
   getline(cin , input);
   
   vector<char> arr;
   for(char ch : input){
       if(ch != ' ') arr.push_back(ch);
   }
   
   sortCharAsInt(arr);
   
   for(char ch: arr){
       cout<<ch<<" ";
   }
    return 0;
}
```

# Complexity

Time Complexity:The algorithm makes a single traversal of the array.
Thus, the time complexity is O(N), where N is the size of the array.


Space Complexity: The algorithm works in-place, using only a few pointers.
Thus, the space complexity is O(1).
