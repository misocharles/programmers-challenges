```swift
func solution(_ array: [Int], _ commands: [[Int]]) -> [Int] {
    var returnArr = [Int]()
    for arr in commands {
        returnArr.append(array[(arr[0]-1)...(arr[1]-1)].sorted()[arr[2]-1])
    }
    return returnArr
}
```
