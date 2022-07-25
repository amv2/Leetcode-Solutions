Java:
```java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int l = 0;                // left pointer
        int r = numbers.length-1; // right pointer
        int[] result = new int[2];
        while (l < r) {
            int sum = numbers[l] + numbers[r];
            // the sum matches the target, return!
            if (sum == target)
                return new int[] {l+1, r+1};
            // the sum was too great, move r
            else if (sum > target) r--;
            // the sum was too small, move l
            else if (sum < target) l++;
        }
        return result;
    }
}
```