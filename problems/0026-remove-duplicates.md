Java:
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int uniques = 1; // pointer to count unique values
        
        // start at index 1 since index 0 is always unique
        for (int i=1; i<nums.length; i++) {
            // if a unique is found, update uniques index
            if (nums[i] != nums[i-1]) {
                nums[uniques] = nums[i];
                uniques++;
            }
        }
        return uniques;
    }
    
}
```
