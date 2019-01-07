```swift
func solution(_ s: String) -> Bool {
    var arr = Array(s.lowercased())
    var appP = arr.filter {
        return $0 == "p"
    }
    var appY = arr.filter {
        return $0 == "y"
    }
    return appP.count == appY.count
}
```
