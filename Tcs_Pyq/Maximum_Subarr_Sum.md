# Maximum Subarray Sum

## Problem Statement:

Given an array of integers, find the contiguous subarray (containing at least one number) that has the largest sum and return its sum.

Write a function that implements the solution to this problem using Kadane's Algorithm.

## Input:
A single line containing a sequence of integers (space-separated). The sequence can include both positive and negative integers.

## Output:
Print the largest sum of a contiguous subarray.

### Example:

#### Input:
```plaintext
-2 1 -3 4 -1 2 1 -5 4
```

#### Output:
```plaintext
6
```

### Explanation:
The contiguous subarray with the largest sum is ```[4, -1, 2, 1],``` with a sum of ```6.```

## Constraints:
- The array will have at least one element.
- The size of the array will be between 1 and 10^5.

# Solution(Brute Force Approach)
```C++
#include <bits/stdc++.h>
using namespace std;

int MaxsubarrSum(int n , vector<int>& arr){
    int maxi = INT_MIN;
    
    for(int i =0 ;i<n ;i++){
        for(int j =i ;j< n ;j++){
            int sum =0;
            for(int k =i ; k < j ;k++){
                
                sum += arr[k];
                
            }
            maxi = max(sum , maxi);
        }
    }
    return maxi;
}

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);

    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
   
    cout<<MaxsubarrSum(n , arr);
    
    return 0;
}
```
## Complexity Analysis

### Time Complexity:O(N^3), 
- where N = size of the array.
- Reason: We are using three nested loops, each running approximately N times.

### Space Complexity: O(1) 
 - as we are not using any extra space.

---

# Solution(Better Approach)
```C++
#include <bits/stdc++.h>
using namespace std;

int MaxsubarrSum(int n , vector<int>& arr){
    int maxi = INT_MIN;
    
    for(int i =0 ;i<n ;i++){
         int sum =0;
        for(int j =i ;j< n ;j++){
           
           sum += arr[j];
           
            maxi = max(sum , maxi);
        }
    }
    return maxi;
}

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);

    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
   
    cout<<MaxsubarrSum(n , arr);
    
    return 0;
}
```
## Complexity Analysis

### Time Complexity: O(N^2), 
- where N = size of the array.
- Reason: We are using two nested loops, each running approximately N times.


### Space Complexity: O(1) a
- as we are not using any extra space.

---

# Optimal Approach
```C++
#include <bits/stdc++.h>
using namespace std;

int MaxsubarrSum(int n , vector<int>& arr){
    int maxi = 0;
    int sum =0;
    for(int i =0 ;i<n ;i++){
        sum += arr[i];
        
        if(sum > maxi){
            maxi = sum;
        }
        if(sum < 0){
            sum =0;
        }
    }
    return maxi;
}

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);

    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
   
    cout<<MaxsubarrSum(n , arr);
    
    return 0;
}
```
## Complexity Analysis

### Time Complexity: O(N),
- where N = size of the array.
- Reason: We are using a single loop running N times.


### Space Complexity: O(1) 
- as we are not using any extra space.

# Follow-up Question(Printing maxsubarray Sum)
There might be more than one subarray with the maximum sum. We need to print any of them.

Intuition: Our approach is to store the starting index and the ending index of the subarray. Thus we can easily get the subarray afterward without actually storing the subarray elements.

If we carefully observe our algorithm, we can notice that the subarray always starts at the particular index where the sum variable is equal to 0, and at the ending index, the sum always crosses the previous maximum sum(i.e. maxi).

So, we will keep a track of the starting index inside the loop using a start variable.
We will take two variables ansStart and ansEnd initialized with -1. And when the sum crosses the maximum sum, we will set ansStart to the start variable and ansEnd to the current index i.e. i.
The rest of the approach will be the same as Kadane’s Algorithm.

## Solution
``` C++
#include <bits/stdc++.h>
using namespace std;

int MaxsubarrSum(int n , vector<int>& arr){
    int maxi = 0;
    int sum =0;
    
    int start =0;
    int ansstart = -1 , ansend = -1;
    
    for(int i =0 ;i<n ;i++){
        if(sum ==0 ) start = i;
        sum += arr[i];
        
        if(sum > maxi){
            maxi = sum;
            
            ansstart = start;
            ansend = i;
        }
        if(sum < 0){
            sum =0;
        }
    }
    
    cout << "The subarray is: [";
    for (int i = ansstart; i <= ansend; i++) {
        cout << arr[i] << " ";
    }
    cout << "]"<<endl;
    return maxi;
}

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);

    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
  
    int maxSum = MaxsubarrSum( n , arr);
    cout << "The maximum subarray sum is: " << maxSum << endl;
    
    return 0;
}
```
### Output:
```plaintext
The subarray is: [4 -1 2 1 ]
The maximum subarray sum is: 6
```

## Complexity Analysis

**Time Complexity:** ```O(N),``` where N = size of the array.
Reason: We are using a single loop running N times.


**Space Complexity:** ```O(1)``` as we are not using any extra space.


