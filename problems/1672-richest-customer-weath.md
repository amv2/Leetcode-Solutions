Java:
```
class Solution {
    public int maximumWealth(int[][] accounts) {
        int richest = 0, sum = 0;
        for (int i=0; i<accounts.length; i++) {
            int[] arr = accounts[i];
            for (int j=0; j<arr.length; j++) {
                sum += arr[j];
            }
            if (sum > richest) {
                richest = sum;
            }
            sum = 0;
        }
        return richest;
    }
}
```
