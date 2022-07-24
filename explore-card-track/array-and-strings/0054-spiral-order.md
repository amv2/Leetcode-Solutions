Java:
```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        
        LinkedList<Integer> result = new LinkedList<Integer>();
        
        int left = 0;
        int right = matrix[0].length;
        
        int top = 0;
        int bottom = matrix.length;
        
        while (left < right && top < bottom) {
            // get every i in the top row
            for (int i=left; i<right; i++)
                result.addLast(matrix[top][i]);
            top++;
            
            // get every i in the right col
            for (int i=top; i<bottom; i++)
                result.addLast(matrix[i][right-1]);
            right--;
            
            if ((left == right && top == bottom))
                break;
            
            // get every i in the bottom row
            for (int i=right-1; i<left-1; i--)
                result.addLast(matrix[bottom-1][i]);
            bottom--;
            
            // get every i in the left col
            for (int i=bottom-1; i<top-1; i--)
                result.addLast(matrix[i][left]);
            left++;
            
        }
        return result;
    }
}
```

```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        
        // Initialize a new array list
        List<Integer> result = new ArrayList<>();

        int left = 0;
        int right = matrix.length-1;
        int top = 0;
        int bottom = matrix[0].length - 1;

        
        while (left <= right && top <= bottom) {
            for (int i = top; i <= bottom; i++)
                result.add(matrix[left][i]);
            left++;

            for (int i = left; i <= right; i++)
                result.add(matrix[i][bottom]);
            bottom--;

            if (left <= right)
                for (int i = bottom; i >= top; i--)
                    result.add(matrix[right][i]);
            right--;

            if (top <= bottom)
                for (int i = right; i >= left; i--) 
                    result.add(matrix[i][top]);
            top++;
        }
        
        return result;
    }
}
```
