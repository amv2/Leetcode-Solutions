Java:
```java
class Solution {
    public int pivotIndex(int[] nums) {
        // calculate the total sum
        int total = 0;
        for (int n : nums) total += n;
        
        // find the left and right sums
        int leftSum = 0, rightSum = 0;
        for (int i=0; i<nums.length; i++) {
            rightSum = total - leftSum - nums[i];
            // check if the current index is the pivot
            if (leftSum == rightSum) return i;
            // update the left sum
            leftSum += nums[i];
        }
        return -1; // no pivot found
    }
}
```
