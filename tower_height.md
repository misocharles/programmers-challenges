```swift
func solution(_ heights:[Int]) -> [Int] {
    var returnArr = Array(repeating: 0, count: heights.count)
    for item in heights.reversed().enumerated() {
        for j in heights.reversed().enumerated() {
            if j.offset > item.offset {
                if j.element > item.element {
                    returnArr[item.offset] = heights.count - j.offset
                    break
                }
            }
        }
    }
    return returnArr.reversed()
}
```
