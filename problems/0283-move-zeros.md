Java:
```java
class Solution {
    public void moveZeroes(int[] nums) {        
        int z = 0; // zero pointer
        int n;     // number pointer
        for (n = 0; n<nums.length; n++) {
            // for non zero numbers, swap with a zero number
            if (nums[n] != 0) {
                nums[z] = nums[z]^nums[n]^(nums[n] = nums[z]);
                z++; // incremenet zero pointer
            }
        }
    }
}
```
