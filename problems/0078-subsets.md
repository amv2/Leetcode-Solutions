Java solution

```java
class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        if (nums.length == 0) return res;
        subsets(nums, 0, new ArrayList<Integer>(), res);
        return res;
    }

    private static void subsets(int[] arr, int i, ArrayList<Integer> output, List<List<Integer>> res) {
        // base case: index == size
        if (i == arr.length){
            res.add(output);
            return;
        }
        //exclude
        subsets(arr, i+1, new ArrayList<>(output), res);
        //include
        output.add(arr[i]);
        subsets(arr, i+1, new ArrayList<>(output), res);
    }
}
```
