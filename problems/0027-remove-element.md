Java:
```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int u = 0; // number of non val numbers
        for (int i=0; i<nums.length; i++)
            if (nums[i] != val) nums[u++] = nums[i];
        return u;
    }
}
```
