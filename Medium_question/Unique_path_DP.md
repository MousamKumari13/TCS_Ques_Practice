# Unique Paths

There is a robot on an ```m x n``` grid. The robot is initially located at the top-left corner (i.e., ```grid[0][0]```). The robot tries to move to the bottom-right corner (i.e., ```grid[m - 1][n - 1]```). The robot can only move either down or right at any point in time.

Given the two integers ```m``` and ```n```, return the number of possible unique paths that the robot can take to reach the bottom-right corner.

The test cases are generated so that the answer will be less than or equal to ```2 * 109```.

Example 1:

## Input: 
```m = 3, n = 7```
## Output: 28
Example 2:

## Input: 
```m = 3, n = 2```
## Output: 3

Explanation: From the top-left corner, there are a total of 3 ways to reach the bottom-right corner:
1. Right -> Down -> Down
2. Down -> Down -> Right
3. Down -> Right -> Down
 
## Constraints:
1 <= m, n <= 100

# Problem Link->
https://leetcode.com/problems/unique-paths/description/

## For Understanding the code  go and check out this video link....
https://youtu.be/iOeoZbHxQqI?si=jDsjhh4rAkrbVXA3

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
int uniquePath(int n , int m){
    vector<vector<int>> dp(n , vector<int>(m , 1));
    
    for(int i = 1 ; i < n ; i++){
        for(int j = 1 ; j < m ;j++){
            dp[i][j] = dp[i-1][j] + dp[i][j-1];
        }
    }
    return dp[n-1][m-1];
}
int main()
{
    int row , column;
    cin>>row>>column;
    
    int result = uniquePath(row,column);
    cout<<result<<endl;
    
    return 0;
}
```
# Complexity
Time Complexity: O(n×m)
Space Complexity: O(n×m)






