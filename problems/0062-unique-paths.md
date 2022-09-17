Rust
```rust
impl Solution {
    pub fn unique_paths(m: i32, n: i32) -> i32 {
        let mut row = vec![1; n as usize];
        for i in (0..m-1) {
            let mut newRow = vec![1; n as usize];
            for j in (0..=n-2).rev() {
                newRow[j as usize] = newRow[(j+1) as usize] + row[j as usize];
            }
            row = newRow;
        }
        return row[0];
    }
}
```