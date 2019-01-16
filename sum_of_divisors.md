```swift
func solution(_ n: Int) -> Int {
    if n == 0 {
        return 0
    }
    var sum = 0
    let sqrt_n = Int(sqrt(Double(n)))
    for i in 1...sqrt_n {
        if n % i == 0 {
            sum = sum + i + Int(n / i)
        }
    }
    return sum
}

```
