```swift
func solution(_ n: Int) -> String {
    return (0..<n).map { i -> String in
        return i % 2 == 0 ? "수" : "박"
    }.joined()
}
```
