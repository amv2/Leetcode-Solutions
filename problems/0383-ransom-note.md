Java:
```java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        // use a letter array
        int[] map = new int[26];
        // get the frequency of each letter in ransomNote
        for (int i = 0; i < magazine.length(); i++)
            map[magazine.charAt(i) - 'a']++;
        // check if the frequencies match in magazine
        for (int j = 0; j < ransomNote.length(); j++) {
            map[ransomNote.charAt(j) - 'a']--;
            if (map[ransomNote.charAt(j) - 'a'] < 0)
                return false;
        }
        return true;
    }
}
```
