Java:
```java
class Solution {
    public int heightChecker(int[] heights) {
        int count = 0;
        int current = 0;
        int[] frequencies = new int[100+1];
        
        // check frequency of heights in the range 0 to 100
        for (int h : heights) frequencies[h]++;
        
        for (int i=0; i<heights.length; i++) {
            // skip heights with frequency of 0
            while (frequencies[current] == 0) current++;
            // count the number of heights that do not match
            if (current != heights[i]) count++;
            // mark the person as checked
            frequencies[current]--;
        }
        return count;
    }
}
```
