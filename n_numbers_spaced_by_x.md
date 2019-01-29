```swift
func solution(_ x: Int, _ n: Int) -> [Int64] {
    var returnArr = [Int64]()
    while returnArr.count < n {
        returnArr.append(Int64(x*(returnArr.count+1)))
    }
    return returnArr
}
```

```swift
func solution(_ x: Int, _ n: Int) -> [Int64] {
    return Array(1...n).map { Int64($0*x) }
}
```
