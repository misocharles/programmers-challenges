```swift
func solution(_ n: Int) -> Int {
    if n < 2 { return n }
    var fibonacci = Array(repeating: 0, count: n+1)
    fibonacci[0] = 0
    fibonacci[1] = 1
    for i in 2...n {
        fibonacci[i] = (fibonacci[i-1] + fibonacci[i-2]) % 1234567
    }
    return fibonacci[n]
}
```
