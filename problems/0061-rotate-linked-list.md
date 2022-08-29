C
```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */


struct ListNode* rotateRight(struct ListNode* head, int k) {
    if (head == NULL) {
        return head;
    }

    int length = 1;
    struct ListNode* tail = head; // pointer to the tail
    while (tail->next != NULL) {
        tail = tail->next;
        length++;
    }
    k = k % length;
    if (k == 0) {
        return head;
    }

    struct ListNode* curr = head;
    for (int i=0; i<length-k-1; i++) {
        curr = curr->next;
    }
    struct ListNode* newHead = curr->next;
    curr->next = NULL;
    tail->next = head;
    return newHead;
}
```