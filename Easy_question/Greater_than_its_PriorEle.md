# Find Count of its element whose value greater than all of its prior elements.
Given an integer array Arr of size N the task is to find the count of elements whose value is greater than all of its prior elements.

***Note*** : 1st element of the array should be considered in the count of the result.

**For example,**
```Arr[]={7,4,8,2,9}```
As 7 is the first element, it will consider in the result.
8 and 9 are also the elements that are greater than all of its previous elements.
Since total of  3 elements is present in the array that meets the condition.
Hence the output = 3.
Example 1:

### Input 
```plaintext
5 -> Value of N, represents size of Arr
7-> Value of Arr[0]
4 -> Value of Arr[1]
8-> Value of Arr[2]
2-> Value of Arr[3]
9-> Value of Arr[4]
```
### Output :
```plaintext
3
```
### Example 2:
```plaintext
5   -> Value of N, represents size of Arr
3  -> Value of Arr[0]
4 -> Value of Arr[1]
5 -> Value of Arr[2]
8 -> Value of Arr[3]
9 -> Value of Arr[4]
```

### Output : 
```plaintext
5
```

**Constraints**
```1<=N<=20```
```1<=Arr[i]<=10000```

## Solution 
```C++
#include <bits/stdc++.h> 
using namespace std;

int greaterVal(vector<int>& arr , int n){
    int count = 1;
    int max = arr[0];
    for(int i = 1 ;i <n ;i++){
        if(arr[i] > max){
            count++;
            max = arr[i];
        }else{
            continue;
        }
    }
    return count;
}
int main()
{
   int n;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   int countGreater = greaterVal(arr , n);
   cout<<countGreater<<endl;
   
    return 0;
}
```

## Complexity

**Time complexity** = ```O(n)```, where 𝑛 is the size of the array.

**Space complexity** = ```O(1)``` since no additional space is used proportional to the input size.
