```swift
func solution(_ phone_number: String) -> String {
    let start = phone_number.index(phone_number.endIndex, offsetBy: -4)
    let end = phone_number.index(phone_number.endIndex, offsetBy: -1)
    var substring = String(phone_number[start...end])
    while substring.count < phone_number.count {
        substring = "*" + substring
    }
    return substring
}
```

```swift
func solution(_ phone_number: String) -> String {
    return String(phone_number.enumerated().map {
        return ($0.offset < phone_number.count - 4) ? Character("*") : $0.element
    })
}
```
