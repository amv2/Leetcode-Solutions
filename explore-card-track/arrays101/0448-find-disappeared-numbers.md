Java:
```java
class Solution {
    public List<Integer> findDisappearedNumbers(int[] nums) {
        // find the range
        int range = nums.length;
        int[] freq = new int[range+1];
        
        // find the frequencies of each number in the range
        for (int i=0; i<nums.length; i++) {
            int index = nums[i];
            freq[index]++;
        }
        
        LinkedList<Integer> result = new LinkedList<Integer>();
        
        // loop through the frequencies
        for (int i=1; i<freq.length; i++)
            // add to the list
            if (freq[i] == 0) 
                result.addLast(i);
        
        return result;
        
    }
}
```
