Java:
```java
class Solution {
    public int[] findDiagonalOrder(int[][] mat) {
        if (mat.length == 1) return mat[0];
        
        int left = 0;
        int right = mat.length;
        int top = 0;
        int bottom = mat[0].length;
        
        int i = 0;
        int[] result = new int[right*bottom];
        
        boolean up = true;
        
        while (left < right && top < bottom) {
            // code logic for travelling up the diagonal
            if (up) {
                // add all the values before the last value
                while (left > 0 && top < bottom-1)
                    result[i++] = mat[left--][top++];
                
                // add the last value
                result[i++] = mat[left][top];
                
                // inc rows if it is the last column
                if (top == bottom-1) left++;
                else top++;
            }
            // reverse logic for travelling down
            else {
                // add all the values before the last value
                while (top > 0 && left < right-1)
                    result[i++] = mat[left++][top--];
                
                // add the last value
                result[i++] = mat[left][top];
                
                // inc cols if it is the last row
                if (left == right-1) top++;
                else left++;
            }
            up = !up; // change loop direction
        }
        return result;
    }
}
```
