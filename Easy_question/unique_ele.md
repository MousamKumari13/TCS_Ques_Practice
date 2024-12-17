# Unique Element
Problem Statement: Given an integer array sorted in non-decreasing order, remove the duplicates in place such that each unique element appears only once. The relative order of the elements should be kept the same.

If there are k elements after removing the duplicates, then the first k elements of the array should hold the final result. It does not matter what you leave beyond the first k elements.

# Note: Return k after placing the final result in the first k slots of the array.

Examples
Example 1:
# Input:
 ```arr[1,1,2,2,2,3,3]```

# Output:
 ```arr[1,2,3,,,,]```


Explanation:
 Total number of unique elements are 3, i.e[1,2,3] and Therefore return 3 after assigning [1,2,3] in the beginning of the array.

Example 2:
# Input:
 ```arr[1,1,1,2,2,3,3,3,3,4,4]```

# Output:
 ```arr[1,2,3,4,,,,,,,_]```


Explanation:
 Total number of unique elements are 4, i.e[1,2,3,4] and Therefore return 4 after assigning [1,2,3,4] in the beginning of the array.

 # Solution
 ``` c++
 #include <bits/stdc++.h>
using namespace std;
int uniqueele(vector<int>& arr ){
    int n = arr.size();
    set<int> unique(arr.begin(), arr.end());
    
    int k =0;
    for(int x : unique){
        arr[k++] = x;
    }
    return k;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);

   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }
   
   int uniq = uniqueele(arr);
   
   for(int i =0 ;i<uniq ;i++){
       cout<<arr[i]<<" ";
   }
   
   cout<<endl;
    return 0;
}
```
# Complexity Analysis
Time Complexity: O(nlogn), n is the size of the array.
O(n) for copying back unique elements into the array.
Space Complexity:O(n) for storing elements in the set