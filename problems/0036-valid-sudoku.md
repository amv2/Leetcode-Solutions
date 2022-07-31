Java:
```java
class Solution {
    public boolean isValidSudoku(char[][] board) {
        HashSet<String> set = new HashSet<>();
        for (int r=0; r<9; r++) {
            for (int c=0; c<9; c++) {
                char curr = board[r][c];
                if (curr != '.' & 
                   (!set.add(curr + "r" + r) || 
                    !set.add(curr + "c" + c) || 
                    !set.add(curr + "b" + r/3 + "-"+ c/3)))
                    return false;
            }
        }
        return true;
    }
}
```