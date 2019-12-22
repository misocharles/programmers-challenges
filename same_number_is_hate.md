# 같은 숫자는 싫어

https://programmers.co.kr/learn/courses/30/lessons/12906

```java
import java.util.*;
public class Solution {
    public int[] solution(int[] arr) {    
        ArrayList<Integer> integers = new ArrayList<Integer>();        
        integers.add(arr[0]);
        for (int i = 1;  i < arr.length; i++) {
            if (arr[i-1] != arr[i]) {
                integers.add(arr[i]);
            }
        }
        int[] answer = new int[integers.size()];
        for (int i=0; i < answer.length; i++) {
            answer[i] = integers.get(i).intValue();
        }
        return answer;
    }
}
```
