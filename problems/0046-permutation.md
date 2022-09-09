Java solution
```java
class Solution {
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        backtrack (0, nums, res);
        return res;
    }
    
    public void backtrack (int pointer, int[] nums, List<List<Integer>> res) {
        if (pointer == nums.length) { 
            List<Integer> l = new ArrayList<>();
            for (int n : nums) { 
                l.add(n);
            }
            res.add(new ArrayList<>(l));
        }
        for (int i = pointer; i < nums.length; i++) {
            swap (i, pointer, nums);
            backtrack (pointer + 1, nums, res);
            swap (i, pointer, nums);
        }
    }

    public void swap (int i, int j, int nums[]) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```