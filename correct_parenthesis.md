# 올바른 괄호

https://programmers.co.kr/learn/courses/30/lessons/12909

```swift
func solution(_ s: String) -> Bool {
    var prevCount = -1
    var compareStr = s
    while prevCount != compareStr.count {
        prevCount = compareStr.count
        compareStr = compareStr.replacingOccurrences(of: "()", with: "")
    }
    if prevCount == 0 {
        return true
    }
    return false
}
```

효율성 해결

```swift
func solution(_ s: String) -> Bool {
    if s[s.index(s.startIndex, offsetBy: 0)] == ")" {
        return false
    }
    if s[s.index(s.endIndex, offsetBy: -1)] == "(" {
        return false
    }
    var count = 0
    for str in s {
        if str == "(" {
            count = count + 1
        } else {
            count = count - 1
        }
        if count == -1 {
            return false
        }
    }
    if count == 0 {
        return true
    }
    return false
}
```
