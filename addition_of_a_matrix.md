```swift
func solution(_ arr1: [[Int]], _ arr2: [[Int]]) -> [[Int]] {
    var returnArr = arr1
    for arr in arr1.enumerated() {
        for i in arr.element.enumerated() {
            returnArr[arr.offset][i.offset] = i.element + arr2[arr.offset][i.offset]
        }
    }
    return returnArr
}
```

```swift
func solution(_ arr1: [[Int]], _ arr2: [[Int]]) -> [[Int]] {
    return arr1.enumerated().map { arr -> [Int] in
        arr.element.enumerated().map({ i -> Int in
            return i.element + arr2[arr.offset][i.offset]
        })
    }
}
```
