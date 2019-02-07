```swift
func solution(_ s: String) -> String {
    return Array(s).enumerated().map {
        if $0.offset == 0 {
            return String($0.element).uppercased()
        }
        if Array(s)[$0.offset-1] == " " {
            return String($0.element).uppercased()
        }
        return String($0.element).lowercased()
    }.joined()
}
```
