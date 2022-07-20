Java:
```java
import java.util.LinkedList;

class Solution {
    public List<String> fizzBuzz(int n) {
        LinkedList<String> list = new LinkedList<String>(); 
        for (int i=1; i<=n; i++) {
            if (i % 3 == 0 && i % 5 == 0) {
                list.addLast("FizzBuzz");
            }
            else if (i % 3 == 0) {
                list.addLast("Fizz");
            } 
            else if (i % 5 == 0) {
                list.addLast("Buzz");
            }
            else {
                list.addLast(Integer.toString(i));
            }
        }
        return list;
    }
}
```
