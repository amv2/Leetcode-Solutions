Java:
```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        int[][] result = new int[numRows][];
        
        for (int i = 0; i < numRows; i++){
            
            int[] row = new int[i+1];
            row[0] = row[i] = 1;
            
            for (int j = 1; j < i; j++)
                row[j] = result[i-1][j-1] + result[i-1][j];
            
            result[i] = row;
        }
        return (List) Arrays.asList(result);
    }
}
```
