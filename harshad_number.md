```swift
func solution(_ x: Int) -> Bool {
    let sum = Array(String(x)).reduce(0) { (Result, Character) -> Int in
        return Result + Int(String(Character))!
    }
    return (x % sum == 0)
}
```
