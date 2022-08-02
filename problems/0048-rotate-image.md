Java
```java
class Solution {
    public void rotate(int[][] matrix) {
        int n = matrix.length;
        for (int i=0; i<=n/2; i++) {
            for (int j=i; j<n-1-i; j++) {
                // save the top left value
                int temp = matrix[i][j];
                // move bottom left to top left
                matrix[i][j] = matrix[n-1-j][i];
                // move bottom right to bottom left
                matrix[n-1-j][i] = matrix[n-1-i][n-1-j];
                // move top right to bottom right
                matrix[n-1-i][n-1-j] = matrix[j][n-1-i];
                // move top left to top right
                matrix[j][n-1-i] = temp;
            }
        }
    }
}
```