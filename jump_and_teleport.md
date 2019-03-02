* 2017 서머코딩 > 점프와 순간 이동
* https://programmers.co.kr/learn/courses/30/lessons/12980

```swift
func solution(_ n: Int) -> Int {
    var ans: Int = 1
    var remain = n
    while remain > 1 {
        if remain % 2 != 0 {
            remain = remain - 1
            ans = ans + 1
        }
        remain = remain / 2
    }
    return ans
}
```
