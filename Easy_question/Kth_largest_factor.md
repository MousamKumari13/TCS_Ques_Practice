 # A positive integer d is said to be a factor of another positive integer N if when N is divided by d, the remainder obtained is zero. For example, for number 12, there are 6 factors 1, 2, 3, 4, 6, 12. Every positive integer k has at least two factors, 1 and the number k itself.Given two positive integers N and k, write a program to print the kth largest factor of N.

Input Format: The input is a comma-separated list of positive integer pairs (N, k)

Output Format: The kth highest factor of N. If N does not have k factors, the output should be 1.

# Constraints:
``` 1<N<10000000000. 1<k<600.You can assume that N will have no prime factors which are larger than 13.```

# Example 1

# Input:
``` 12,3```
# Output:
``` 4```
# Explanation: N is 12, k is 3. The factors of 12 are (1,2,3,4,6,12). The highest factor is 12 and the third largest factor is 4. The output must be 4

# Example 2

# Input: 
```30,9```

# Output: 
```1```
# Explanation: N is 30, k is 9. The factors of 30 are (1,2,3,5,6,10,15,30). There are only 8 factors. As k is more than the number of factors, the output is 1.

# Solution

``` c++
int main() {
   int n , k;
   cin>>n >>k;
  
  vector<int> res;
  for(int i = 1; i< sqrt(n) ;i++){
      if(n % i == 0){
          res.push_back(i); 
          if(i != n/i){
              res.push_back(n/i); 
          }
      }
  }
  sort(res.rbegin() , res.rend()); //reversing 
  
  if(k < res.size()){ 
      cout<<res[k-1]<<endl;
  }else{
      cout<<"1"<<endl;
  }
    return 0;
}
```