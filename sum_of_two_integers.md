```swift
func solution(_ a:Int, _ b:Int) -> Int64 {
    
    if a > b {
        return solution(b, a)
    }
    var sum: Int64 = 0
    for i in a...b {
        sum = sum + Int64(i)
    }
    return sum
}
```
