```swift
func solution(_ n: Int) -> Int {
    var count = 0
    var arr = [Int](2...n)
    for _ in arr {
        if let num = arr.first {
            arr = arr.filter{ $0 % num != 0 }
            count = count + 1
        } else {
            return count
        }
    }
    return count
}
```
