```swift
func solution(_ n: Int) -> Int {
    var answer: Int = n
    var countAnswer = -1
    let count1 = Array(String(n, radix: 2)).filter { return $0 == "1" }.count
    while count1 != countAnswer {
        answer = answer + 1
        countAnswer = Array(String(answer, radix: 2)).filter { return $0 == "1" }.count
    }
    return answer
}
```

```swift
func solution(_ n: Int) -> Int {
    var answer: Int = n + 1
    while n.nonzeroBitCount != answer.nonzeroBitCount {
        answer = answer + 1
    }
    return answer
}
```
