```swift
func solution(_ bridge_length: Int, _ weight: Int, _ truck_weights: [Int]) -> Int {
    var time = 0
    var waiting = truck_weights
    var taking = [Int]()
    var taking_time = [Int]()
    var completed = [Int]()
    
    while completed.count < truck_weights.count {
        time = time + 1
        taking_time = taking_time.map { $0 + 1 }
        if let truck_time = taking_time.first, truck_time == bridge_length {
            completed.append(taking.removeFirst())
            taking_time.removeFirst()
        }
        if let truck = waiting.first {
            if taking.reduce(0, +) + truck <= weight {
                taking.append(waiting.removeFirst())
                taking_time.append(0)
            }
        }
    }
    return time
}
```
