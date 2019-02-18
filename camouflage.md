```swift
func solution(_ clothes: [[String]]) -> Int {
    var arr = [String: [String]]()
    clothes.map {
        if arr[$0[1]] == nil {
            arr[$0[1]] = [String]()
        }
        arr[$0[1]]?.append($0[0])
    }
    
    if arr.count == 1 {
        return clothes.count
    }
    
    return clothes.count + arr.reduce(1, { (result: Int, element: (key: String, value: [String])) -> Int in
        return result * element.value.count
    })
}
```
