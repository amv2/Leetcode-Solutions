Java:
```java
class Solution {
    public int dominantIndex(int[] nums) {
        // find the index of the largest element
        int index = 0;
        for (int i=1; i<nums.length; i++)
            if (nums[i] > nums[index])
                index = i;
        
        // check if the largest element is at least
        // twice as big as every other element
        for (int n : nums) {
            // skip the largest element
            if (n == nums[index]) continue;
            // if the criteria is not met
            else if (nums[index] < n*2) return -1;
        }
        return index; // otherwise return its index
    }
}
```
