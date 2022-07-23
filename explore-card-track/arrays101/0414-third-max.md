Java:
```java
class Solution {
    public int thirdMax(int[] nums) {
        Integer[] max = new Integer[3]; // 3 is the third max
        
        for (Integer n : nums) {
            // if n is a duplicate, continue
            if (n.equals(max[0]) || n.equals(max[1]) || n.equals(max[2])) {
                continue;
            }
            
            // check n with first, second, and third max
            // and if it is null, update the max values
            if (max[0] == null || n > max[0]) {
                max[2] = max[1];
                max[1] = max[0];
                max[0] = n;
            } else if (max[1] == null || n > max[1]) {
                max[2] = max[1];
                max[1] = n;
            } else if (max[2] == null || n > max[2]) {
                max[2] = n;
            }
        }
        // return the first max if the third 
        // max is null at the end of the loop
        if (max[2] == null) {
            return max[0];
        }
        
        // otherwise return the third max
        return max[2];
    }
}
```
