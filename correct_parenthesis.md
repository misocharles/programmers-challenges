```swift
func solution(_ s: String) -> Bool {
    var prevCount = -1
    var compareStr = s
    while prevCount != compareStr.count {
        prevCount = compareStr.count
        compareStr = compareStr.replacingOccurrences(of: "()", with: "")
    }
    if prevCount == 0 {
        return true
    }
    return false
}

```
