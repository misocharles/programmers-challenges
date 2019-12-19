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

해결 못하고 다시 풀었다

```swift
func solution(_ numbers: [Int]) -> String {
    let str = numbers.compactMap {
            return String($0)
        }.sorted(by: { (s1, s2) -> Bool in
            if s1 == s2 {
                return s1 > s2
            }
            if s1[s1.startIndex] == s2[s2.startIndex] {
                for i in 0..<s1.count*s2.count {
                    let c1 = s1[ s1.index(s1.startIndex, offsetBy: (i % s1.count)) ]
                    let c2 = s2[ s2.index(s2.startIndex, offsetBy: (i % s2.count)) ]
                    if c1 != c2 {
                        return c1 > c2
                    }
                }
            }
            return s1 > s2
        }).joined()
    if str[str.startIndex] == "0" {
        return "0"
    }
    return str
}
```

그런데. 다른 사람 풀이에서 s1+s2 > s2+s1 문자열을 합친 후 비교하는 걸 보니, 왜 이렇게 어렵게 돌아갔는지 한 방 맞은 기분이 들었다.

그리고 내 식대로 다시 품. 해결 방법이 이렇게 차이가 나다니.

```swift
func solution(_ numbers: [Int]) -> String {
    let str = numbers.map { String($0) }.sorted { $0+$1 > $1+$0 }.joined()
    return str.first == "0" ? "0" : str
}
```
