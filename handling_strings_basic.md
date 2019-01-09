```swift
func solution(_ s: String) -> Bool {
    if s.count != 4 && s.count != 6 {
        return false
    }
    return (s.rangeOfCharacter(from: CharacterSet.decimalDigits.inverted) == nil)
}
```
