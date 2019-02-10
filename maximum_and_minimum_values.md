```swift
func solution(_ s: String) -> String {
    let arr = s.split(separator: " ").compactMap { Int($0) }.sorted()
    return "\(arr.first!) \(arr.last!)"
}
```

```swift
func solution(_ s: String) -> String {
    let arr = s.split(separator: " ").compactMap { Int($0) }
    return "\(arr.min()!) \(arr.max()!)"
}
```
