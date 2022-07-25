Java:
```java
class Solution {
    public String reverseWords(String s) {
        StringBuilder sb = new StringBuilder();
        s = new StringBuilder(s).reverse().toString();
        String s1[] = s.trim().split(" ");
        for (int i=s1.length-1; i>=0; i--)
            if (!s1[i].isEmpty()) {
                sb.append(s1[i]);
                sb.append(" ");
            }
        return sb.toString().trim();
    }
}
```