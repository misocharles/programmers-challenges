```swift
func solution(_ n: Int, _ words: [String]) -> [Int] {
    var count = 0
    while count < words.count {
        let user = count % n
        if count > 0 && words[count].first! != words[count-1].last! {
            return [(count % n) + 1, (count / n) + 1]
        }
        if words.index(of: words[count])! != count {
            return [(count % n) + 1, (count / n) + 1]
        }
        count = count + 1
    }
    return [0, 0]
}
```
