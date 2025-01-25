# Ceil The Floor

Problem statement
You're given a sorted array 'a' of 'n' integers and an integer 'x'.
Find the floor and ceiling of 'x' in 'a[0..n-1]'.

***Note:***
Floor of 'x' is the largest element in the array which is smaller than or equal to 'x'.
Ceiling of 'x' is the smallest element in the array greater than or equal to 'x'.


Example:
### Input:
```plaintext 
n=6, x=5, a=[3, 4, 7, 8, 8, 10]   
```
### Output:
```
4
```
Explanation:
The floor and ceiling of 'x' = 5 are 4 and 7, respectively.

Detailed explanation ( Input/output format, Notes, Images )

### Sample Input 1 :
```plaintext
6 8
3 4 4 7 8 10
```

### Sample Output 1 :
```plaintext
8 8
```
Explanation of sample input 1 :
Since x = 8 is present in the array, it will be both floor and ceiling.

### Sample Input 2 :
```plaintext
6 2
3 4 4 7 8 10
```
### Sample Output 2 :
```plaintext
-1 3
```
Explanation of sample input 2 :
Since no number is less than or equal to x = 2 in the array, its floor does not exist. The ceiling will be 3.

### Constraints :
```plaintext
1 <= n <= 2 * 10^5      
1 <= a[i] <= 10^9
Time limit: 1 sec
```
# Problem link->
https://www.naukri.com/code360/problems/ceiling-in-a-sorted-array_1825401?topList=tcs-interview-questions&problemListRedirection=true&leftPanelTabValue=PROBLEM&count=25&page=1&search=&sort_entity=order&sort_order=ASC&customSource=studio_nav

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;

int findFloor(vector<int> &a, int n, int x) {
    int ans = -1, low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (a[mid] <= x) {
            ans = a[mid];
            low = mid + 1;
        } else {
            high = mid - 1;
        }
    }
    return ans;
}

int findCeil(vector<int> &a, int n, int x) {
    int ans = -1, low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (a[mid] >= x) {
            ans = a[mid];
            high = mid - 1;
        } else {
            low = mid + 1;
        }
    }
    return ans;
}

pair<int, int> getFloorAndCeil(vector<int> &a, int n, int x) {
    int f = findFloor(a, n, x);
    int c = findCeil(a, n, x);
    return make_pair(f, c);
}

int main() {
    int n, q;
    cin >> n >> q;

    vector<int> arr(n);
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    while (q--) {
        int x;
        cin >> x;
        pair<int, int> result = getFloorAndCeil(arr, n, x);
        cout << "Floor: " << result.first << ", Ceil: " << result.second << endl;
    }

    return 0;
}
```
## Complexity
**Time Complexity** : ```O(logn).```
***findFloor and findCeil***: Binary search runs in O(logn) for each function.
***getFloorAndCeil:*** Calls findFloor and findCeil, so its complexity is 
```O(logn)+O(logn)=O(logn).```
Driver Code:For q queries, total complexity = O(q⋅logn).


**Space Complexity:** ```O(1).```
No additional space is used apart from variables.
This implementation is efficient and handles multiple queries on a sorted array effectively.
