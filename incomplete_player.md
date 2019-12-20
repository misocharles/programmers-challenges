# 완주하지 못한 선수

https://programmers.co.kr/learn/courses/30/lessons/42576

## JAVA

```java
import java.util.*;
class Solution {
    public String solution(String[] participant, String[] completion) {
        List<String> list = new ArrayList<>(Arrays.asList(participant));
        for (int i = 0; i < completion.length; i++) {
            String player = completion[i];
            boolean result = list.remove(player);
            if (result == false) {
                return player;
            }
        }
        return list.get(0);
    }
}
```

위 코드는 효율성 테스트에 실패함. `ArrayList.remove()` 때문이라고 함.

```java
import java.util.*;
class Solution {
    public String solution(String[] participant, String[] completion) {        
        Arrays.sort(participant); 
        Arrays.sort(completion);
        for (int i = 0; i < completion.length;i++) {
            if (participant[i].equals(completion[i]) == false) {
                return participant[i];
            }
        }
        return participant[participant.length-1];
    }
}
```
