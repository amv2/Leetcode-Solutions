Java:
```java
class Solution {
    public int[] runningSum(int[] nums) {
        int size = nums.length, sum = 0;
        int[] result = new int[size];
        for (int i=0; i<size; i++) {
            sum += nums[i];
            result[i] = sum;
        }
        return result;
    }
}
```
