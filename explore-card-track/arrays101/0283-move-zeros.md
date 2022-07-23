Java:
```java
class Solution {
    public void moveZeroes(int[] nums) {        
        int z = 0; // zero pointer
        int n;     // number pointer
        for (n = 0; n<nums.length; n++) {
            // for non zero numbers, swap with a zero number
            if (nums[n] != 0) {
                int temp = nums[z];
                nums[z] = nums[n];
                nums[n] = temp;
                z++; // incremenet zero pointer
            }
        }
    }
}
```
