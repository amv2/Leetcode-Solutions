Java:
```java
class Solution {
    public void duplicateZeros(int[] arr) {
        int zeros = 0, index = 0, size = arr.length;
        for (int i : arr) if (i == 0) zeros++;
        int[] newArr = new int[size + zeros];
        for (int i=0; i<size; i++) {
            if (arr[i] == 0) {
                newArr[index] = arr[i];
                newArr[index++] = 0;
            }
            else newArr[index] = arr[i];
            arr[i] = newArr[i];
            index++;
        }
    }
}
```
30 / 30 test cases passed.
Status: Accepted
Runtime: 2 ms
Memory Usage: 46 MB

```java
class Solution {
    public void duplicateZeros(int[] arr) {
        int index = 0;
        ArrayList<Integer> newArr = new ArrayList<Integer>();
        for (int i=0; i<arr.length; i++) {
            if (arr[i] == 0) {
                newArr.add(index, 0);
                newArr.add(index++, 0);
            }
            else newArr.add(index, arr[i]);
            arr[i] = newArr.get(i);
            index++;
        }
    }
}
```

30 / 30 test cases passed.
Status: Accepted
Runtime: 3 ms
Memory Usage: 46.8 MB
