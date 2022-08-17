C
```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */


bool isPalindrome(struct ListNode* head){
    struct ListNode* p1 = head; // fast
    struct ListNode* p2 = head; // slow

    // find the middle node
    while (p1 != NULL && p1->next != NULL) {
        p1 = p1->next->next;
        p2 = p2->next;
    }

    // reverse the second half of the list
    struct ListNode* prev = NULL;
    struct ListNode* temp = NULL;
    while (p2 != NULL) {
        temp = p2->next;
        p2->next = prev;
        prev = p2;
        p2 = temp;
    }

    // check palindrome
    p1 = head; // left pointer
    p2 = prev; // right pointer
    while (p2 != NULL) {
        if (p1->val != p2->val) return false;
        p1 = p1->next;
        p2 = p2->next;
    }
    return true;
}
```