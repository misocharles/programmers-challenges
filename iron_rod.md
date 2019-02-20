```swift
func solution(_ arrangement: String) -> Int {
    var depth = -1
    var answer = 0
    var pop = Character(".")
    for c in arrangement {
        if c == "(" {
            depth = depth + 1
        } else if pop == "(" {
            answer = answer + depth
            depth = depth - 1
        } else {
            answer = answer + 1
            depth = depth - 1
        }
        pop = c
    }
    return answer
}
```
