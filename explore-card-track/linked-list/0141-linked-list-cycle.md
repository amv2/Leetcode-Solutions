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
    public boolean hasCycle(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;
        
        while (fast != null) {
            try {
                slow = slow.next;
                fast = fast.next.next;

                if (slow == fast) return true;
            } catch (Exception e) {
                return false;
            }
        }
        return false;
    }
}
```