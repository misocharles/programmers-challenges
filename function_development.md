```swift
func solution(_ progresses: [Int], _ speeds: [Int]) -> [Int] {
    var answer = [Int]()
    var progressingIndex = 0
    var workedDay = 0
    while progressingIndex < progresses.count {
        workedDay = workedDay + 1
        if progresses[progressingIndex] + speeds[progressingIndex] * workedDay >= 100 {
            var completedCount = 0
            while progressingIndex < progresses.count && progresses[progressingIndex] + speeds[progressingIndex] * workedDay >= 100 {
                completedCount = completedCount + 1
                progressingIndex = progressingIndex + 1
            }
            answer.append(completedCount)
        }
    }
    return answer
}
```
