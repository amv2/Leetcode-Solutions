Rust
```rust
impl Solution {
    pub fn search_range(nums: Vec<i32>, target: i32) -> Vec<i32> {
        if nums.len() == 0 {
            return vec![-1, -1];
        }
        // left, middle, and right index
        let (mut li, mut ri, mut mi) = (0, nums.len()-1, 0);

        while li <= ri {
            mi = li + (ri - li) / 2;
            // if the target is found
            if nums [mi] == target {
                // find the start index
                for i in (li..=mi) {
                    if nums[i] == target{
                        li = i;
                        break;
                    }
                }
                // find the end index
                for i in (mi..=ri).rev() {
                    if nums[i] == target {
                        ri = i;
                        break;
                    }
                }
                return vec![li as i32, ri as i32];
            }
            // otherwise update the indexes
            else if nums[mi] < target {
                li = mi + 1;
            } else {
                if mi == 0 {
                    break;
                }
                ri = mi-1;
            }
        }
        vec![-1, -1]
    }
}
```