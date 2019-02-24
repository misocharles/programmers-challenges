```swift
func solution(_ numbers: String) -> Int {
    
    var arr = Array(numbers)
    var sel = Array(repeating: "", count: numbers.count)
    var visit = Array(repeating: false, count: numbers.count)
    var num = Set<Int>()
    
    func perm(_ n: Int, _ r: Int, _ k: Int) {
        if k == r {
            num.insert(Int(sel.joined()) ?? 0)
            return
        }
        
        for i in 0..<n {
            if visit[i] { continue }
            visit[i] = true
            sel[k] = String(arr[i])
            perm(n, r, k+1)
            visit[i] = false
        }
    }
    
    var answer = 0
    for i in 1...numbers.count {
        perm(numbers.count, i, 0)
    }
    
    func primenumber(_ num: Set<Int>) -> Int {
        var count = 0
        var arr = Array(num)
        count = arr.filter {
            if $0 == 0 || $0 == 1 {
                return false
            }
            for i in 2..<Int(sqrt(Double($0))) {
                if $0 % i == 0 {
                    return false
                }
            }
            return true
        }.count
        return count
    }
    
    answer = primenumber(num)
    return answer
}
```
