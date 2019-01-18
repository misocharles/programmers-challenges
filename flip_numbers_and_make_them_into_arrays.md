```swift
func solution(_ n: Int64) -> [Int] {
    return String(n).reversed().map { Int(String($0)) ?? 0 }
}
```

```swift
func solution(_ n: Int64) -> [Int] {
    return String(n).reversed().compactMap{ Int(String($0)) }
}
```
