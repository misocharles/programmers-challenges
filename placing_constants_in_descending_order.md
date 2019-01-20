```swift
func solution(_ n: Int64) -> Int64 {
    let s = String(n).sorted { return $0 > $1 }
    return Int64(String(s))!
}
```
