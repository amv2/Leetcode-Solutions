Java:
```java
class Solution {
    public int numberOfSteps(int num) {
        int steps = 0;
        while (num > 0) {
            if (num % 2 == 0) num /= 2;
            else num -= 1;
            steps++;
        }
        return steps;
    }
}
```

Rust
```rust
impl Solution {
    pub fn number_of_steps(num: i32) -> i32 {
        let mut num = num;
        let mut steps = 0;
        while num > 0 {
            if num % 2 == 0 {
                num /= 2;
            } else {
                num -= 1;
            }
            steps += 1;
        }
        steps
    }
}
```

Rust recursion
```rust
impl Solution {
    pub fn number_of_steps(num: i32) -> i32 {
        if num == 0 {
            return 0;
        }
        let mut steps = num;
        if steps % 2 == 0 {
            steps /= 2;
        } else {
            steps -= 1;
        }
        Self::number_of_steps(steps) + 1
    }
}
```