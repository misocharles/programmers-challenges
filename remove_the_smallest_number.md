```swift
func solution(_ arr: [Int]) -> [Int] {
    var returnArr = [Int]()
    let a = arr.sorted { $0 > $1 }
    for (index, element) in a.enumerated() {
        if index > 0 {
            if a[index-1] != element {
                returnArr.append(element)
            }
        } else {
            returnArr.append(element)
        }
    }
    returnArr.removeLast()
    if returnArr.count == 0 {
        return [-1]
    }
    return returnArr
}
```
