```swift
func solution(_ num: Int) -> Int {
    return solution(num, 1)
}

func solution(_ num: Int, _ count: Int) -> Int {
    if count >= 500 {
        return -1
    }
    if num % 2 != 0 {
        return solution(num * 3 + 1, count + 1)
    } else if num / 2 != 1 {
        return solution(num / 2, count + 1)
    }
    return count
}
```
