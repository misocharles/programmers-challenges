```swift
func solution(_ s: String) -> String {
    return s.split(separator: " ").map { str -> String in
        return str.enumerated().map { (offset: Int, element: Character) -> String in
            if offset % 2 == 0 {
                return String(element).uppercased()
            }
            return String(element).lowercased()
        }.joined()
    }.joined(separator: " ")
}
```

```swift
func solution(_ s: String) -> String {
    var charIndex = 0
    return s.enumerated().map { (offset: Int, element: Character) -> String in
        if element == " ") {
            charIndex = 0
        } else {
            charIndex = charIndex + 1
            if charIndex % 2 == 1 {
                return String(element).uppercased()
            }
            return String(element).lowercased()
        }
        return String(element)
    }.joined()
}
```
