```swift
func GCD(_ a: Int, _ b: Int) -> Int {
    if a % b != 0 {
        return GCD(min(a, b), a % b)
    }
    return b
}

func LCM(_ n: Int, _ m: Int) -> Int {
    if m % n == 0 {
        return m
    }
    let gcd = GCD(max(n, m), min(n, m))
    return m * n / gcd
}

func solution(_ arr: [Int]) -> Int {
    return arr.reduce(1, { (s1: Int, s2: Int) -> Int in
        return LCM(s1, s2)
    })
}
```
