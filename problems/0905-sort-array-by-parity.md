Java:
```java
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        int o = 0; // odd pointer
        int e;     // even pointer
        for (e = 0; e<nums.length; e++) {
            // for non zero numbers, swap with a zero number
            if (nums[e] % 2 == 0) {
                int temp = nums[o];
                nums[o] = nums[e];
                nums[e] = temp;
                o++; // incremenet odd pointer
            }
        }
        return nums;
    }
}
```
