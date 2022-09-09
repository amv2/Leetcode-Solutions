Java solution:
```java
class Solution {

    String[] store = {"abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"};
    List<String> res = new ArrayList<String>();
    
    public List<String> letterCombinations(String digits) {   
        if (digits.length() == 0)  return res;
        backtrack(digits, 0, new StringBuilder());     
        return res;   
    }
    
    private void backtrack(String digits, int i, StringBuilder sb) {
        if (i == digits.length()) {
            res.add(sb.toString());
            return;
        }
        String temp = store[digits.charAt(i)-50];
        for (char c : temp.toCharArray()) {
            sb.append(c);
            backtrack(digits, i+1,sb);
            sb.deleteCharAt(sb.length()-1);
        }  
    }
}
```