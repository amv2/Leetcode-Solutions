Java:
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
    public ListNode middleNode(ListNode head) {
        ListNode current = head;
        int size = 0;
        // find the size of the list
        while (current != null) {
            current = current.next;
            size++;
        }
        // find the middle node
        int middle = size / 2;
        current = head;
        while (middle != 0) {
            current = current.next;
            middle--;
        }
        return current;
    }
}
```
