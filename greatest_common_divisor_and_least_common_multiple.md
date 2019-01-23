```swift
func solution(_ n: Int, _ m: Int) -> [Int] {
    if m % n == 0 {
        return [n, m]
    }
    
    let gcd = (Int(sqrt(Double(min(n, m))))...min(n, m))
        .filter { return min(n, m) % $0 == 0 }
        .filter { return max(n, m) % $0 == 0 }
        .last!
    let lcm = m * n / gcd
    return [gcd, lcm]
}
```

```swift
func solution(_ n: Int, _ m: Int) -> [Int] {
    if m % n == 0 {
        return [n, m]
    }
    
    func GCD(_ a: Int, _ b: Int) -> Int {
        if a % b != 0 {
            return GCD(min(a, b), a % b)
        }
        return b
    }
    
    let gcd = GCD(max(n, m), min(n, m))
    let lcm = m * n / gcd
    return [gcd, lcm]
}
```
