Java:
```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        StringBuilder res = new StringBuilder();
        
        // since the prefix is common with all elements
        // only one string needs to be checked (str[0])
        for (int i=0; i<strs[0].length(); i++)
            // check each character of each string
            for (String s : strs)
                if (i==s.length() || s.charAt(i) != strs[0].charAt(i))
                    return res.toString();
            res.append(strs[0].charAt(i));
        
        return res.toString();
    }
}
```
