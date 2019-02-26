* 탐욕법(Greedy) > 조이스틱
* https://programmers.co.kr/learn/courses/30/lessons/42860

```swift
func solution(_ name: String) -> Int {
    let sum = Array(name.utf8).map { (value) -> Int in
        return min(Int(value-65), Int(91-value))
    }.reduce(0, +)
    
    var moveRightCount = 0
    for item in name.enumerated() {
        if (name.suffix(name.count-item.offset).filter { $0 != "A" }).count == 0 {
            break
        }
        moveRightCount = item.offset
    }
    
    var moveLeftCount = 0
    let reversedName = String(name.dropFirst().reversed())
    for item in reversedName.enumerated() {
        if (reversedName.suffix(reversedName.count-item.offset).filter { $0 != "A" }).count > 0 {
            moveLeftCount = moveLeftCount + 1
            continue
        }
    }
    return sum + min(moveLeftCount, moveRightCount)
}
```
