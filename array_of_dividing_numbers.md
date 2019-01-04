```swift
func solution(_ arr: [Int], _ divisor: Int) -> [Int] {
    var returnArr = arr.filter({$0 % divisor == 0})
    if returnArr.count == 0 {
        return [-1]
    }
    returnArr.sort()
    return returnArr
}
```
