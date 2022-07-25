Java:
```java
class Solution {
    public int arrayPairSum(int[] nums) {
        Arrays.sort(nums);
        int sum = 0;
        for (int i=0; i<nums.length; i+=2)
            sum += nums[i];
        return sum;
    }
}
```

Alternate Solution:
```java
class Solution {
    public int arrayPairSum(int[] nums) {
        quicksort(nums, 0, nums.length - 1); 
        int sum = 0;
        for (int i=0; i<nums.length; i+=2)
            sum += nums[i];
        return sum;
    }
    
    // Quicksort implementation
    public void quicksort(int[] arr, int low, int high){
        if (low < high) {
            int p = low, j;
            for (j=low+1; j<=high; j++)
                if(arr[j] < arr[low])
                    swap(arr, ++p, j);

            swap(arr, low, p);
            quicksort(arr, low, p-1);
            quicksort(arr, p+1, high);
        }
    }
    
    public void swap(int[] arr, int low, int pivot){
        int tmp = arr[low];
        arr[low] = arr[pivot];
        arr[pivot] = tmp;
    }
}
```