Java solution:

```java
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> res = new ArrayList<>();
        generateParenthesis(res, "", 0, 0, n);
        return res;
    }

    private void generateParenthesis(List<String> res, String s, int open, int close, int n) {
        if (open == n && close == n) {
            res.add(s);
            return;
        }
        // if open parentheses is less than the given n
        if (open < n) {
            generateParenthesis(res, s + "(", open + 1, close, n);
        }
        // if we need more close parentheses to balance
        if (close < open) {
            generateParenthesis(res, s + ")", open, close + 1, n);
        }
    }
}
```
