# Rotate array by K elements : Block Swap Algorithm

Problem Statement: Given an array of n size, rotate the array by k elements using the Block Swap Algorithm.

# Examples:

Example 1:
# Input: 
``` N = 5, array[] = {1,2,3,4,5} K=2 ```

# Output: 
``` {3,4,5,1,2}```


Explanation: Rotate the array to right by 2 elements.

Example 2:
# Input: 
```N = 7, array[] = {1,2,3,4,5,6,7} K=3```

# Output:
``` {4,5,6,7,1,2,3}```


Explanation: Rotate the array to right by 3 elements.

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void swap(vector<int>& arr , int start1 , int start2 , int size){
    for(int i =0 ;i< size ;i++){
        swap(arr[start1 + i] ,arr[start2 + i]);
    }
}
void blockswapRotate(vector<int>& arr , int n , int k){
    k = k% n;
    if(k == 0 ) return;
    int i = k;
    int j = n-k;
    while(i != j){
        if(i<j){
        swap(arr , k -i , k + j -i, i);
        j -= i;
        }else{
            swap(arr , k - i ,k ,j);
            i -= j;
        }
    }
    swap(arr ,k-i , k ,i);
}
int main() {
   int n ,k;
   cin>>n>>k;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   blockswapRotate(arr , n ,k);
   
   for(int num :arr){
       cout<<num<<" ";
   }
   cout<<endl;
    return 0;
}
```
# Complexity:
Time Complexity:𝑂(𝑛)
Space Complexity:𝑂(1)

# Block-swap Algorithm 

For Understanding Block-swap Algo please checkout this youtube video url - 
https://youtu.be/kCKWws9aTYw?si=baYQ2NZhrDh_xHeI

# Program without using block-swap algo  . APPROACH 2nd ->

``` C++
#include <bits/stdc++.h>
using namespace std;

void rotate(vector<int>& nums, int k) {
    int n = nums.size();
    vector<int> temp(n);
    for (int i = 0; i < n; i++) {
        temp[(i + k) % n] = nums[i];
    }
    nums = temp;
}
int main() {
    int n, k;
    cin >> n;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    cin >> k;
    rotate(nums, k);
    for (int num : nums) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}
```
# Explaination of this code is given below

Iteration of the Loop:

i	(i + k) % n	     nums[i]	   temp after assignment
0	(0 + 2) % 5 = 2	   1	          {0, 0, 1, 0, 0}
1	(1 + 2) % 5 = 3	   2	          {0, 0, 1, 2, 0}
2	(2 + 2) % 5 = 4	   3	          {0, 0, 1, 2, 3}
3	(3 + 2) % 5 = 0	   4	          {4, 0, 1, 2, 3}
4	(4 + 2) % 5 = 1	   5	          {4, 5, 1, 2, 3}

# Complexity:
Time Complexity:𝑂(𝑛)
Space Complexity:𝑂(𝑛)

# Approach 3rd

``` C++
#include <bits/stdc++.h>
using namespace std;

void reverse(vector<int>& nums, int low, int high) {
    while (low < high) {
        swap(nums[low], nums[high]);
        low++;
        high--;
    }
}
// Function to rotate the array to the right by k steps
void rotate(vector<int>& nums, int n, int k) {
    k = k % n; // Handle cases where k >= n
    reverse(nums, 0, n - k - 1); // Reverse the first part
    reverse(nums, n - k, n - 1); // Reverse the second part
    reverse(nums, 0, n - 1); // Reverse the entire array
}

int main() {
    int n, k;
    cin >> n;
    cin >> k;

    vector<int> nums(n);
     for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    rotate(nums, n, k);
    for (int num : nums) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}
```
# Explaination 
For Understanding Algo please checkout this youtube video url - 
https://youtu.be/ENcnXXiRT6E?si=5DeaC_2m23mZfiNR

# Complexity:
Time Complexity : o(n)
First call: 𝑂(𝑛−𝑘)
Second call: 𝑂(𝑘)
Third call: 𝑂(𝑛)
Adding these up: 𝑂(𝑛−𝑘)+𝑂(𝑘)+𝑂(𝑛)=𝑂(𝑛)O(n−k)+O(k)+O(n)=O(n).

Space complexity: 𝑂(1)
