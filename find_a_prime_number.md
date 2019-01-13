```swift
func solution(_ n: Int) -> Int {
    var count = 0
    var arr = [Int](2...n)
    for _ in arr {
        if let num = arr.first {
            arr = arr.filter{ $0 % num != 0 }
            count = count + 1
        } else {
            return count
        }
    }
    return count
}
```


```swift
import Foundation
func solution(_ n: Int) -> Int {
    var count = 0
    var arr = [Int](2...n)
    let sqrt_n = sqrt(Double(n))
    for _ in arr {
        if let num = arr.first {
            if Double(num) >= sqrt_n {
                return count + arr.count
            } else {
                arr = arr.filter{ $0 % num != 0 }
                count = count + 1
            }
        } else {
            return count
        }
    }
    return count
}
```
