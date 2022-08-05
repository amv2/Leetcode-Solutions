Java
```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode detectCycle(ListNode head) {
        if (head == null || head.next == null) return null;
        
        ListNode slow = head;
        ListNode fast = head;
        while (slow != null && fast != null){
            slow = slow.next;
            fast = fast.next;
            if (fast != null) fast = fast.next;
            if (slow == fast) break;
        }
        if (fast == null) return null;
        
        slow = head;
        while (slow != fast){
            slow = slow.next;
            fast = fast.next;
        }
        return slow;

    }
}
```

C
```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode *detectCycle(struct ListNode *head) {
    if (head == NULL || head->next == NULL) return NULL;
    ListNode* slow = head;
    ListNode* fast = head;
    while (slow != NULL && fast != NULL) {
        slow = slow->next;
        fast = fast->next;
        if (fast != NULL) fast = fast->next;
        if (slow == fast) break;
    }
    if (fast == NULL) return NULL;
    slow = head;
    while (slow != fast) {
        slow = slow->next;
        fast = fast->next;
    }
    return slow;
}
```

C++
```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        if (head == NULL || head->next == NULL) return NULL;
        ListNode* slow = head;
        ListNode* fast = head;
        while (slow != NULL && fast != NULL) {
            slow = slow->next;
            fast = fast->next;
            if (fast != NULL) fast = fast->next;
            if (slow == fast) break;
        }
        if (fast == NULL) return NULL;
        slow = head;
        while (slow != fast) {
            slow = slow->next;
            fast = fast->next;
        }
        return slow;
    }
};
```