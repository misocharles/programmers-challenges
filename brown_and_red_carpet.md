```swift
func solution(_ brown: Int, _ red: Int) -> [Int] {
    for n in 1...Int(sqrt(Double(red))) {
        if (n+2)*(red/n+2) == brown + red {
            return [(red/n+2), n+2]
        }
    }
    return [0, 0]
}
```

```swift
func solution(_ brown: Int, _ red: Int) -> [Int] {
    for n in (1...Int(sqrt(Double(red)))).reversed() {
        if (red/n+2) * (n+2) == (brown + red) {
            return [(red/n+2), n+2]
        }
    }
    return [0, 0]
}
```
