* 2017 팁스타운 > 예상 대진표
* https://programmers.co.kr/learn/courses/30/lessons/12985

```swift
func solution(_ n: Int, _ a: Int, _ b: Int) -> Int {
    func square(_ n: Int, _ s: Int = 1) -> Int {
        if n / 2 == 1 { return s }
        return square(n / 2, s + 1)
    }
    let squareOfn = square(n)
    
    for i in 1...squareOfn {
        let num = pow(Double(2), Double(i))
        if ceil(Double(a) / num) == ceil(Double(b) / num) {
            return i
        }
    }
    return 1
}
```
