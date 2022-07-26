Java:
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        Arrays.sort(nums1);
        Arrays.sort(nums2);
        List<Integer> list = new ArrayList<>();
        int i = 0, j = 0;
        while (i<nums1.length & j<nums2.length) {
            if (nums1[i] < nums2[j]) 
                i++;
            else if (nums1[i] > nums2[j]) 
                j++;
            else {
                list.add(nums1[i]);
                i++; j++;
            }
        }
        i = 0;
        int [] res = new int[list.size()];
        for (int n : list) res[i++] = n;
        return res;
    }
}
```

Alternate Solution:
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        Map<Integer,Integer> map = new HashMap<>();
        for (int i : nums1)
            map.put(i, map.getOrDefault(i,0)+1);   
        ArrayList<Integer> interSec = new ArrayList<>();
        for (int i : nums2){
            if (map.getOrDefault(i, 0) >= 1){
                interSec.add(i);
                map.put(i, map.getOrDefault(i,0)-1);
            }
        }
        return interSec.stream().mapToInt(i -> i).toArray();    
    }
}
```