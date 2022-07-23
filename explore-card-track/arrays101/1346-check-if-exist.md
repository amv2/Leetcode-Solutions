Java:
```java
class Solution {
    public boolean checkIfExist(int[] arr) {
        // use a set to store uniques
        HashSet<Integer> set = new HashSet<>();
        
        for (int n : arr) {
            if (set.contains(n)) return true;
            // add all numbers * 2 to the set
            set.add(n * 2);
            // if a number is even, add 
            // the number halved to the set
            if (n % 2 == 0) set.add(n / 2);
        }
        return false; // no number found
    }
}
```
