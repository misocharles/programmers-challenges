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
