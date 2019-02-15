```swift
func solution(_ numbers: [Int]) -> String {
    return numbers.compactMap {
        return String($0)
    }.sorted(by: { (s1, s2) -> Bool in
        if s1.count == 1 {
            if s1.prefix(1) == s2.prefix(1)  {
                return String(repeating: s1, count: s2.count) > s2
            }
        }
        if s2.count == 1 {
            if s1.prefix(1) == s2.prefix(1)  {
                return s1 > String(repeating: s2, count: s1.count)
            }
        }
        return s1 > s2
    }).joined()
}
```

```
solution([12, 121]) // 12121 12112
solution([21, 212]) // 21212 21221
```

```swift
func solution(_ numbers: [Int]) -> String {
    return numbers.compactMap {
        return String($0)
    }.sorted(by: { (s1, s2) -> Bool in
        if s1.prefix(1) == s2.prefix(1)  {
            if s1.count != s2.count {
                return s1.suffix(1) > s2.suffix(1)
            }
        }
        return s1 > s2
    }).joined()
}
```
