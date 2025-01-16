### Question:
**Write a program that sorts students based on their marks and displays the top K students with their marks.**

- The program should take input in a single line consisting of the number K (the number of top students to display), followed by N (the total number of students), and then a list of student marks and names. 
- For example, each student is represented by their marks followed by their name, and this repeats for N students.
- The program should display the names of the top K students based on their marks in descending order. If there are fewer than K students, display all of them.

**Input Format:**

K N marks1 name1 marks2 name2 ... marksN nameN


*Output Format:*
For the top K students, display their names and marks:

name1: marks1
name2: marks2
...


*Example Input:*
```plaintext
3 5 90 Alice 85 Bob 95 Charlie 80 David 70 Eve
```

*Example Output:*
```plaintext
Charlie: 95
Alice: 90
Bob: 85

 ```

---

### Explanation:
- The input consists of a list of student marks and names.
- The program stores each student as a pair of marks and name.
- It then sorts the students in descending order of marks.
- Finally, it displays the top K students.

## Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void Topper(int k ,int  n ,vector<pair<int , string>>& marks){
    sort(marks.begin() , marks.end(), [](const pair<int , string>& a , const pair<int , string>& b){
        return a.first > b.first;
    });
    
    for(int i = 0 ; i < k ; i++){
        cout<<marks[i].second<<" : "<<marks[i].first<<endl;
    }
}
int main()
{
    int k , n;
    cin>>k>> n;
    
    vector<pair<int , string>> marks(n);
    for(int i =0 ;i<n ;i++){
        cin>>marks[i].first>>marks[i].second;
    }
    
    Topper(k , n , marks);
    return 0;
}
```
## Complexity
 ### Time Complexity: 
 - **O(n log n + k)** (simplifies to O(n log n) for large n).


### Space Complexity: **O(log n).**