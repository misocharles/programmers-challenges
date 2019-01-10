
```swift
func solution(_ seoul: [String]) -> String {
    let index = seoul.firstIndex(of: "Kim") ?? 0
    return "김서방은 \(index)에 있다"
}
```

```swift
func solution(_ seoul: [String]) -> String {
    for (index, text) in seoul.enumerated() {
        if text == "Kim" {
            return "김서방은 \(index)에 있다"
        }
    }
    return ""
}
```
