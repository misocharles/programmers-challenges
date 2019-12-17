```swift
func solution(_ s: String) -> Bool {
    if s.count != 4 && s.count != 6 {
        return false
    }
    return (s.rangeOfCharacter(from: CharacterSet.decimalDigits.inverted) == nil)
}
```

프로그래머스에서 안 푼 걸로 나와서 다시 품

```swift
func solution(_ s: String) -> Bool {
    if s.count != 4 && s.count != 6 {
        return false
    }
    guard let i = Int(s) else {
        return false
    }
    return true
}
```
