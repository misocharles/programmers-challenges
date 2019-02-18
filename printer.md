```swift
func solution(_ priorities: [Int], _ location: Int) -> Int {
    var arr = priorities
    var nowLocation = location
    var count = 0
    
    while arr.count > 0 {
        let n = arr.removeFirst()
        if n < arr.max() ?? 1 {
            arr.append(n)
            if nowLocation == 0 {
                nowLocation = arr.count
            }
        } else {
            count = count + 1
        }
        nowLocation = nowLocation - 1
        if nowLocation == -1 {
            return count
        }
    }
    return 0
}
```
