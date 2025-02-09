# Swapping Nodes in LinkedList

Ram gave Shyaam a challenge, he gave shyaam the head of a linked list, and an integer k. He asked Shyaam to swap the values of the Kth node from the beginning and the Kth node from the end (the list is 1-indexed).

***Note:*** The number of nodes in the list is N.

**Input Format**

The first line contains an integer N, representing the number of nodes in the linked list.

The second line contains N space-separated integers, each representing the value of a node in the linked list.

The third line contains an integer K, indicating the positions of the nodes to be swapped.

**Output Format**

Output the linked list after swapping the values of the two specified nodes.

**Constraints**
```plaintext
1 <= K <= N <= 10^5

0 <= Node.val <= 10^2
```
## Testcase Input
```plaintext
5

1 2 3 4 5

2
```
## Testcase Output
```plaintext
1 4 3 2 5
```

## Problem Link ->
https://leetcode.com/problems/swapping-nodes-in-a-linked-list/description/

## For understanding the approach of this program, watch this video ->
   https://youtu.be/TxryJMerDwE?si=xPl-pQ67b40ohBi5

# Solution
``` c++
#include <bits/stdc++.h>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(NULL) {}
};

int findlength(ListNode* head) {
    int l = 0;
    while (head) {
        head = head->next;
        l++;
    }
    return l;
}

ListNode* swapNodes(ListNode* head, int k) {
    int l = findlength(head);

    int k_1 = k;
    ListNode* Node1 = head;
    while (k_1 > 1) {
        Node1 = Node1->next;
        k_1--;
    }
    
    int k_2 = l - k + 1;
    ListNode* Node2 = head;
    while (k_2 > 1) {
        Node2 = Node2->next;
        k_2--;
    }
    swap(Node1->val, Node2->val);
    
    return head;
}

ListNode* createList(int arr[], int n) {
    ListNode* head = new ListNode(arr[0]);
    ListNode* temp = head;

    for (int i = 1; i < n; i++) {
        temp->next = new ListNode(arr[i]);
        temp = temp->next;
    }

    return head;
}

void printList(ListNode* head) {
    while (head) {
        cout << head->val << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    int N, K;
    cin >> N;
    int arr[N];
    for (int i = 0; i < N; i++) cin >> arr[i];
    cin >> K;

    ListNode* head = createList(arr, N);
    head = swapNodes(head, K);
    
    printList(head);
    
    return 0;
}
```
## Complexity
### Time Complexity
Finding the length (findlength):``` O(N)```
Finding the Kth nodes: ```O(N)```
Swapping values: ```O(1)```
🔹 ***Total Time Complexity: O(N)***

### Space Complexity
Uses only a few pointers ```(O(1))```
🔹 ***Total Space Complexity: O(1) (constant space)***

## Approach 2nd
```C++
#include <bits/stdc++.h>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(NULL) {}
};

ListNode* swapNodes(ListNode* head, int k) {
         ListNode* p1 = NULL;
         ListNode* p2 = NULL;

         ListNode* temp = head;
         while(temp != NULL){

            if(p2 != NULL){
                p2 = p2->next;
            }

            k-- ;
            if(k ==0){
                p1 = temp;
                 p2 = head;
            }
           temp = temp->next;
        }
        swap(p1->val , p2->val);
        return head;

     }

ListNode* createList(int arr[], int n) {
    ListNode* head = new ListNode(arr[0]);
    ListNode* temp = head;

    for (int i = 1; i < n; i++) {
        temp->next = new ListNode(arr[i]);
        temp = temp->next;
    }

    return head;
}

void printList(ListNode* head) {
    while (head) {
        cout << head->val << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    int N, K;
    cin >> N;
    int arr[N];
    for (int i = 0; i < N; i++) cin >> arr[i];
    cin >> K;

    ListNode* head = createList(arr, N);
    head = swapNodes(head, K);
    
    printList(head);
    
    return 0;
}
```
## Complexity

### Time Complexity
Single traversal of the linked list → ```O(N)```
🔹 ***Total Time Complexity: O(N)***

### Space Complexity
Only a few pointer variables used → ```O(1)```
🔹 ***Total Space Complexity: O(1) (constant space)***
