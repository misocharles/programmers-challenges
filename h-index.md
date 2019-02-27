* 정렬 > H-Index
* https://programmers.co.kr/learn/courses/30/lessons/42747 

```swift
func solution(_ citations: [Int]) -> Int {
    var h_index = 0
    for item in citations.sorted().enumerated() {
        if (citations.filter{ $0 >= item.element }).count >= item.element {
            h_index = item.element
        }
    }
    return h_index
}
```

문제 설명이 이상하고 정답도 맞지 않는다.
