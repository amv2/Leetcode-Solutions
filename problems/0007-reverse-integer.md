Java:
```java
class Solution {
    public int reverse(int x) {
        long res = 0;
        while (x != 0) {
            res = (res*10) + x % 10;
            x /= 10;
        }
        if (res > Integer.MAX_VALUE || 
            res < Integer.MIN_VALUE) 
            return 0;
        return (int) res;
    }
}
```

Alternate Solution:
```java
class Solution {
    public int reverse(int x) {
        boolean neg = false;
        if (x < 0) {
            x = -x;
            neg = true;
        }
        char[] chars = ("" + x).toCharArray();
        int l = 0, r = chars.length-1;
        while (l < r) {
            char temp = chars[l];
            chars[l++] = chars[r];
            chars[r--] = temp;
        }
        try {
            x = Integer.parseInt(new String(chars));
        } catch (Exception e) {
            x = 0;
        }
        return neg ? -x : x;
    }
}
```