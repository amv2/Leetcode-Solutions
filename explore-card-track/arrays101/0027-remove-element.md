Java:
```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int p = 0; // pointer to val
        for (int i=0; i<nums.length; i++) {
            if (nums[i] != val) {
                nums[p] = nums[i]; // swap the indexes
                p++; // increment the pointer
            }
        }
        return p;
    }
}
```
