Rust
```rust
impl Solution {
    pub fn can_jump(nums: Vec<i32>) -> bool {
        let mut goal = (nums.len()-1) as i32;
        for i in (0..nums.len()-1).rev() {
            if (i as i32) + nums[i as usize] >= goal {
                goal = i as i32;
            }
        }
        return goal == 0;
    }
}
```