Java:
```java
class Solution {
    public int[] plusOne(int[] digits) {
        int i = digits.length-1;
        
        while (true) {
            // if no carry over is necessary
            if (i >= 0) {
                // add 1 to all numbers except 9
                if (digits[i] == 9)
                    digits[i] = 0;
                else {
                    digits[i] += 1;
                    break;
                }
            }
            // otherwise copy the elements to a larger array
            else {
                int[] copy = new int[digits.length+1];
                for (int j=1; j<copy.length; j++) 
                    copy[j] = digits[j-1];
                // add 1 and assign digits to equal the copy
                copy[0] = 1;
                digits = copy;
                break;
            }
            i--;
        }
        return digits;
    }
}
```
