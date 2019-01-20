```swift
func solution(_ n: Int64) -> Int64 {
    let sqrt_n = sqrt(Double(n))
    if (sqrt_n - Double(Int(sqrt_n))) != 0 {
        return -1
    }
    return Int64((sqrt_n+1) * (sqrt_n+1))
}
```
