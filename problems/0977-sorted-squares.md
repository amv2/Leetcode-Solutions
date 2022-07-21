Java:
```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] result = new int[nums.length];
        int lp = 0, rp = nums.length - 1, index = rp;
        while (lp <= rp) {
            if (nums[lp]*nums[lp] > nums[rp]*nums[rp]) {
                result[index] = nums[lp]*nums[lp];
                lp++;
            }
            else {
                result[index] = nums[rp]*nums[rp];
                rp--;
            }
            index--;
        }
        return result;
    }
}
```
