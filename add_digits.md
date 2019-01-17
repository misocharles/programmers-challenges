```swift
func solution(_ n: Int) -> Int {
    return String(n).map { c -> Int in
            return Int(String(c)) ?? 0
        }.reduce(0) { $0 + $1 }
}
```
