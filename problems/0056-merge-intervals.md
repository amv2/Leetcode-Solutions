Rust
```rust
impl Solution {
    pub fn merge(mut intervals: Vec<Vec<i32>>) -> Vec<Vec<i32>> {
        if intervals.len() <= 1 {
            return intervals;
        }
        intervals.sort_by_key(|k| k[0]);
        let mut res = Vec::new(); // result vec
        let (mut si, mut ei) = (intervals[0][0], intervals[0][1]);
        for interval in intervals.iter() {
            if interval[0] <= ei {
                ei = std::cmp::max(ei, interval[1]);
            } else {
                res.push(vec![si, ei]);
                si = interval[0];
                ei = interval[1];
            }
                
        }
        res.push(vec![si, ei]);
        res
    }
}
```