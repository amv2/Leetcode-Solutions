Java:
```java
class Solution {
    public int strStr(String haystack, String needle) {        
        char[] h = haystack.toCharArray();
        char[] n = needle.toCharArray();
        
        for (int i=0; i < h.length + 1 - n.length; i++)
            for (int j=0; j < n.length; j++) {
                if (h[i+j] != n[j]) 
                    break;
                if (j == n.length -1) 
                    return i;
            }
        return -1;
    }
}
```
