Java:
```java
class Solution {
    public int strStr(String haystack, String needle) {
        // if (needle.length() == 0) return 0;
        // if (needle.length() > haystack.length()) return -1;
        
        char[] h = haystack.toCharArray();
        char[] n = needle.toCharArray();
        int index = 0, counter = 0;
        
        // loop thru the haystack
        for (int i = 0; i < h.length; i++) {
            // if the first character of the needle is found
            if (h[i] == n[0]) {
                index = i;
                // loop thru the needle until false
                for (int j = 0; j < n.length; j++) {
                    if (index == h.length || h[index] != n[j]) {
                        break;
                    }
                    index++;
                    counter++;
                }
                // if it goes thru, return the index
                if (counter == n.length) return i;
            }
        }
        return -1;
    }
}
```
