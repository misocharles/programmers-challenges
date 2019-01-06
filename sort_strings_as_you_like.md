```swift
func solution(_ strings: [String], _ n: Int) -> [String] {
    return strings.sorted(by: {
        let index0 = $0.index($0.startIndex, offsetBy: n)
        let index1 = $1.index($1.startIndex, offsetBy: n)
        switch $0[index0] {
        case $1[index1]:
            return $0 < $1
        default:
            return $0[index0] < $1[index1]
        }
    })
}
```
