Java:
```java
class Solution {
    public void rotate(int[] nums, int k) {
        k = k % nums.length;
        
        // reverse the entire array: [1,2,3,4,5]
        int l = 0, r = nums.length-1;
        while (l < r) {
            nums[l] = nums[l]^nums[r]^(nums[r] = nums[l]);
            l++; r--;
        }
        
        // reverse until the kth element: [1,2,3]
        l = 0; r = k-1;
        while (l < r) {
            nums[l] = nums[l]^nums[r]^(nums[r] = nums[l]);
            l++; r--;
        }
        
        // reverse the remaining elements: [4,5]
        l = k; r = nums.length - 1;
        while (l < r) {
            nums[l] = nums[l]^nums[r]^(nums[r] = nums[l]);
            l++; r--;
        }
    }
}
```