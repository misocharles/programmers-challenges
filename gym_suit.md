* 탐욕법(Greedy) > 체육복
* https://programmers.co.kr/learn/courses/30/lessons/42862

```swift
func solution(_ n: Int, _ lost: [Int], _ reserve: [Int]) -> Int {
    var people = Array(repeating: 1, count: n)
    for i in reserve {
        people[i-1] = 2
    }
    for i in lost {
        if people[i-2] == 2 {
            people[i-1] = 1
            people[i-2] = 1
        } else if i < n && people[i] == 2 {
            people[i-1] = 1
            people[i] = 1
        } else {
            people[i-1] = 0
        }
    }
    return people.filter { $0 > 0 }.count
}
```

* 수정

```swift
func solution(_ n: Int, _ lost: [Int], _ reserve: [Int]) -> Int {
    var people = Array(repeating: 1, count: n)
    for i in reserve {
        people[i-1] = 2
    }
    for i in lost {
        people[i-1] = people[i-1] - 1
    }
    for i in 0..<people.count {
        if people[i] > 0 {
            continue
        }
        if i < n-1 && people[i+1] == 2 {
            people[i+1] = 1
            people[i] = 1
        } else if i > 0 && people[i-1] == 2 {
            people[i-1] = 1
            people[i] = 1
        } else  {
            people[i] = people[i] - 1
        }
    }
    return people.filter { $0 > 0 }.count
}
```
