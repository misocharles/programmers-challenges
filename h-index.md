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

(수정) 불현듯이 citations 없는 자연수가 아닐까 생각이 들었다. 

```swift
func solution(_ citations:[Int]) -> Int {
    var h_index = 0
    let sorted = citations.sorted { $0 > $1 }
    for (index, element) in sorted.enumerated() {
        if (element >= index + 1) {
            h_index = index + 1
        }
    }
    return h_index
}
```

```swift
func solution(_ citations: [Int]) -> Int {
    var h_index = 0
    for i in 0...(citations.max()!) {
        if (citations.filter{ $0 >= i }).count >= i {
            h_index = i
        }
    }
    return h_index
}
```
