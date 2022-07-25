Java:
```java
class Solution {
    public int[] findDiagonalOrder(int[][] mat) {
        if (mat.length == 1) return mat[0];
        
        int m = mat.length;
        int n = mat[0].length;
        
        int i = 0;
        int row = 0;
        int col = 0;
        int[] result = new int[m*n];
        
        boolean up = true;
        
        while (row < m && col < n) {
            // code logic for travelling up the diagonal
            if (up) {
                // add all the values before the last value
                while (row > 0 && col < n-1)
                    result[i++] = mat[row--][col++];
                
                // add the last value
                result[i++] = mat[row][col];
                
                // inc rows if it is the last column
                if (col == n-1) row++;
                else col++;
            }
            // reverse logic for travelling down
            else {
                // add all the values before the last value
                while (col > 0 && row < m-1)
                    result[i++] = mat[row++][col--];
                
                // add the last value
                result[i++] = mat[row][col];
                
                // inc cols if it is the last row
                if (row == m-1) col++;
                else row++;
            }
            up = !up; // change loop direction
        }
        return result;
    }
}
```
