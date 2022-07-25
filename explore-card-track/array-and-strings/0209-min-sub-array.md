Java:
```java
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int l = 0; // left pointer
        int sum = 0, res = Integer.MAX_VALUE;
        
        // r is the right pointer
        for (int r=0; r<nums.length; r++) {
            sum += nums[r];
            while (sum >= target) {
                if (res > r-l+1) res = r-l+1;
                sum -= nums[l];
                l++;
            }
        }
        return res == Integer.MAX_VALUE ? 0 : res;
    }
}
```