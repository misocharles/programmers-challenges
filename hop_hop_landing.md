```swift
func solution(_ land: [[Int]]) -> Int {
    var answer = 0
    var prevSeletedIndex = -1
    for row in land {
        let maxItem = row.enumerated().max { (item1, item2) -> Bool in
            if item2.offset == prevSeletedIndex {
                return false
            }
            return item1.element < item2.element
        }
        prevSeletedIndex = maxItem?.offset ?? -1
        answer = answer + (maxItem?.element ?? 0)
    }
    return answer
}
```
