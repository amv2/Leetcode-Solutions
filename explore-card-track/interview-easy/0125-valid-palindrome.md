Java:
```java
class Solution {
    public boolean isPalindrome(String s) {
        int l = 0;            // left pointer
        int r = s.length()-1; // right pointer
        s = s.toLowerCase();
        while (l < r) {
            char start = s.charAt(l);
            char end = s.charAt(r);
            if (!Character.isLetterOrDigit(start)) {
                l++;
                continue;
            }
            if (!Character.isLetterOrDigit(end)) {
                r--;
                continue;
            }
            if (start != end) return false;
            l++; r--;    
        }
        return true;
    }
}
```

Alternate Solution: (800+ms)
```java
class Solution {
    public boolean isPalindrome(String s) {
        s = s.replaceAll("[^a-zA-Z0-9]+", "").toLowerCase();
        return s.equals(new StringBuilder(s).reverse().toString());
    }
}
```