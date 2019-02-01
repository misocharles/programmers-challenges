```swift
func solution(_ d: [Int], _ budget :Int) -> Int {
    var sum = 0
    for i in d.sorted().enumerated() {
        sum = sum + i.element
        if sum > budget {
            return i.offset
        }
    }
    return d.count
}
```
