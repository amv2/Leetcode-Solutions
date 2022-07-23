Java:
```java
class Solution {
    public int[] replaceElements(int[] arr) {
        int newMax, rightMax = -1; // initial value -1
        // iterate through the array backwards
        for (int i=arr.length-1; i>=0; i--) {
            // check if the rightMax or prev val is bigger
            newMax = rightMax > arr[i] ? rightMax : arr[i];
            // replace current value with rightMax
            arr[i] = rightMax;
            // update rightMax
            rightMax = newMax;
        }      
        return arr;
    }
}
```
