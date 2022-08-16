Java
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode curr = head;
        while (curr != null) {
            if (curr.val == val) {
                curr = curr.next;
                head = curr;
            }
            else if (curr.next != null && curr.next.val == val)
                curr.next = curr.next.next;
            else curr = curr.next;
        }
        return head;
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
struct ListNode* removeElements(struct ListNode* head, int val){
    struct ListNode* curr = head;
    while (curr != NULL){
        if (curr->val == val) {
            curr = curr->next;
            head = curr;
        }
        else if (curr->next != NULL && curr->next->val == val)
            curr->next = curr->next->next;
        else curr = curr->next;
    }
    return head;
}
```