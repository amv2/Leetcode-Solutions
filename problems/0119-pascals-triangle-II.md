Java:
```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        int[][] result = new int[rowIndex+1][];
        
        for (int i = 0; i < rowIndex+1; i++){
            
            int[] row = new int[i+1];
            row[0] = row[i] = 1;
            
            for (int j = 1; j < i; j++)
                row[j] = result[i-1][j-1] + result[i-1][j];
            
            result[i] = row;
        }
        return Arrays.stream(result[rowIndex]).boxed().toList();
    }
}
```

Alternate Solution:
```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<Integer> res = new ArrayList();
        for(int i=0; i<=rowIndex; i++) {
            res.add(0, 1);
            for(int j=1; j<res.size()-1; j++) 
                res.set(j, res.get(j) + res.get(j+1));
        }            
        return res;
    }
}
```