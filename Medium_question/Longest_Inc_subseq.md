# Longest Increasing Subsequence

Alice has introduced a new online game which has N levels i e., 1 to N. She wants to get reviews for each level of this game so she will launch only a single level of game on any particular day, and on that day users of this game are allowed to play only that particular level. As there are N levels so it will take exactly N days to launch all levels of the game, it is not necessary that level of game will be launched in increasing order, she will pick any random level on particular day and launch it, and it is obvious that any level of the game can’t be launched twice. After completing the level, the user will give reviews and she will give them one reward unit for each level the user will complete. Alice has put one constraint on users that only after completing any level of game, user will be able to play higher levels. For E.g. If Alice has launched the 3rd level of the game on the first day and if any user completes it then he will get one reward point, but now. he can’t play the game with level 1 and level 2.

# NOTE:
 If a user wants to skip to play on any number of days, he is free to do that.

You are the best gamer, so you can easily complete all levels. As you want to maximize your reward points, you want to play as many levels as you can. Alice has already announced the order in which she will launch levels of his game, your aim is to maximize your reward points.

Given number of levels of games(N) and order of level of games launched one by one on each day. You have to output maximum reward points you can earn.

Hint: You will play any game if and only if that number is becoming the part of the longest subsequence in array of order of games.

Example 1:

# Input:
```5 -> N = 5```
```2 1 3 4 5 -> ``` Order of levels, Alice will launch one by one
# Output:
```4```

Explanation:
If Alice plays the 2nd level of the game on the first day, then he will not be able to play the 1st level of the game on the 2nd day. As after completing the 2nd level, he will be able to play higher levels. From 3rd day he can play all upcoming levels as those levels are in increasing order. So, possible sequences of levels of games played to maximize rewards points are [2, 3, 4, 5] or [1, 3, 4, 5]. In both cases he will get 4 reward points.
Example 2:

# Input:
```5 -> N = 5```
```5 4 3 2 1 ```-> Order of levels, Alice will launch one by one
# Output:
```1```

Explanation:
Alice has launched levels in decreasing order, so he will be able to play exactly one level of game. After playing any level, there are no higher levels on coming days, so maximum reward point is 1.

# Solution 
```c++
#include <bits/stdc++.h>
using namespace std;

int solve(vector<int>& arr ,int n , int idx , int prev, vector<vector<int>>& dp){
   
    if(idx == n) return 0;
    
    if(dp[idx][prev+1] != -1){
        return dp[idx][prev+1];
    }
    
    int skip = 0+  solve( arr , n , idx+1 , prev , dp);
     
    int take =0;
    if(prev == -1 || arr[idx] > arr[prev]){
        take = 1 + solve(arr, n , idx+1 , idx , dp);
    }

    return dp[idx][prev+1] = max(take, skip);
}
int LIS(vector<int>& arr , int n){
     n= arr.size();
   vector<vector<int>> dp(n , vector<int>(n+1 , -1));
    return solve(arr,n , 0 , -1 , dp);
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);

   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }

  int result = LIS(arr, n);
  
  cout<<result<<endl;
    return 0;
}
```
# Approach using Recursion and memoization (DP)
for understanding this problem check out this link - https://youtu.be/DG50PJIx2SM?si=WzTeQNLJ6oZRBMmq
2nd ->>> https://youtu.be/ekcwMsSIzVc?si=HHiHu7UCpJdAJ6a1

# Complexity
Time Complexity: O(N*N)

Reason: There are N*N states therefore at max ‘N*N’ new problems will be solved.

Space Complexity: O(N*N) + O(N)

Reason: We are using an auxiliary recursion stack space(O(N)) (see the recursive tree, in the worst case we will go till N calls at a time) and a 2D array ( O(N*N+1)).

# problem link -> 
01) https://leetcode.com/problems/longest-increasing-subsequence/submissions/1480976242/
02) https://www.naukri.com/code360/problems/longest-increasing-subsequence_630459?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf

# Solution (BY using Buttom-Up Approach)

```C++
#include <bits/stdc++.h>
using namespace std;

int lengthOfLIS(vector<int>& arr , int n){
     n= arr.size();
     
     vector<int> t(n , 1);
     int maxLis = 1;
     
     for(int i =0 ;i< n ;i++){
         for(int j = 0 ; j< i ;j++){
             if(arr[j] < arr[i]){
                 t[i] = max(t[i] , t[j] + 1);
                 maxLis = max(maxLis , t[i]);
             }
         }
     }
     return maxLis;
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);

   for(int i =0 ;i< n ;i++){
       cin>>arr[i];
   }

  int result = lengthOfLIS(arr, n);
  
  cout<<result<<endl;
    return 0;
}
```
# Complexity
Time Complexity: 𝑂(𝑛^2)
Space Complexity:O(n)

For understanding this Concept watch this vid -> https://youtu.be/h9rm4N8XbL0?si=SAyOD5oA_KAQwhs5