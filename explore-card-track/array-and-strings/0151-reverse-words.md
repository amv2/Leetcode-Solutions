Java:
```java
class Solution {
    public String reverseWords(String s) {
        StringBuilder sb = new StringBuilder();
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

Alternate Solution:
```java
class Solution {
    public String reverseWords(String s) {
        String[] words = s.trim().split("\\s+");
        for (int i = 0; i < words.length; i++) {
            words[i] = words[i].replaceAll("[^\\w]", "");
        }

        // reverse the entire array
        int l = 0, r = words.length-1;
        while (l < r) {
            String temp = words[l];
            words[l++] = words[r];
            words[r--] = temp;
        }
        StringBuffer sb = new StringBuffer();
        for(int i=0; i<words.length-1; i++) {
            sb.append(words[i] + " ");
        }
        sb.append(words[words.length-1]);
        return sb.toString();
    }
}
```