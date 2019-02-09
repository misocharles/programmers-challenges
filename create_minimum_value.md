```swift
func solution(_ A: [Int], _ B: [Int]) -> Int {
    let a = A.sorted()
    let b = [Int](B.sorted().reversed())    
    var sum = 0
    for i in 0..<a.count {
        sum = sum + a[i] * b[i] 
    }
    return sum
}
```

```swift
func solution(_ A: [Int], _ B: [Int]) -> Int {
    let a = A.sorted(by: >)
    let b = B.sorted(by: <)
    var sum = 0
    for i in 0..<a.count {
        sum = sum + a[i] * b[i]
    }
    return sum
}
```
