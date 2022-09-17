Rust
```rust
use std::cmp::Ordering::*;
impl Solution {
    pub fn search_matrix(matrix: Vec<Vec<i32>>, target: i32) -> bool {
        let (mut x, mut y) = (0i32, (matrix[0].len()-1) as i32);
        while x <= (matrix.len() - 1) as i32 && y >= 0 {
            match matrix[x as usize][y as usize].cmp(&target) {
                Equal => return true,
                Less => x += 1,
                Greater => y -= 1,
            }
        }
        false
    }
}
```

Rust alternate solution
```rust
impl Solution {
    pub fn search_matrix(matrix: Vec<Vec<i32>>, target: i32) -> bool {
        let (mut r, mut c) = (0i32, (matrix[0].len()-1) as i32);
        while r < (matrix.len() as i32) && c >= 0 {
            if matrix[r as usize][c as usize] == target {
                return true;
            }
            else if matrix[r as usize][c as usize] > target {
                c -= 1;
            } else {
                r += 1;
            }
        }
        return false;
    }
}
```

Java
```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int row = 0;
        int col = matrix[0].length-1;
        while (row < matrix.length && col >= 0){
            if (target > matrix[row][col]) row++;
            else if (target < matrix[row][col]) col--;
            else return true;
        }
        return false;
    }
}
```