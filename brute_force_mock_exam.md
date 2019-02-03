```swift
func solution(_ answers: [Int]) -> [Int] {
    
    let guessArr = [[1,2,3,4,5], [2,1,2,3,2,4,2,5], [3,3,1,1,2,2,4,4,5,5]]
    var correct = [0,0,0]
    
    answers.enumerated().map { (offset: Int, element: Int) -> Void in
        for i in 0..<3 {
            let guess = guessArr[i][offset % guessArr[i].count]
            if guess == element {
                correct[i] = correct[i] + 1
            }
        }
    }
    return correct.enumerated().map { (offset: Int, element: Int) -> Int in
        if correct.sorted().reversed()[0] == element {
            return offset + 1
        }
        return 0
    }.filter {
        $0 != 0
    }
}
```
