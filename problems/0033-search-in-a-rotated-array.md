Rust
```rust
impl Solution {
    pub fn search(nums: Vec<i32>, target: i32) -> i32 {
        let (mut li, mut ri) = (0, nums.len()-1);
        while li <= ri {
            let mi = li + (ri-li) / 2;
            if nums[mi] == target {
                return mi as i32;
            } 
            if nums[li] <= nums[mi] {
                if nums[mi] < target || nums[li] > target {
                    li = mi+1;
                } else {
                    ri = mi-1;
                }
            } else {
                if nums[mi] > target || nums[ri] < target {
                    ri = mi-1;
                } else {
                    li = mi+1;
                }
            }
        }
        -1
    }
}
```