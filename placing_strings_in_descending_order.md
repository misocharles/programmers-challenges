```swift
func solution(_ s: String) -> String {
    return String(Array(s).sorted {
        return $0 > $1
    })
}
```
