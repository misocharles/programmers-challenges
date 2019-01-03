```
func solution(_ s:String) -> String {
    let midIndex = s.index(s.startIndex, offsetBy: s.count/2-(1-s.count%2))
    let endIndex = s.index(midIndex, offsetBy: 1-s.count%2)
    return String(s[midIndex...endIndex])
}
```
