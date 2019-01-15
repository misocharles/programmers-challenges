```swift
func solution(_ s: String, _ n: Int) -> String {
    let t = s.utf8.map { str -> UInt8 in
        if str == 32 {
            return 32
        }
        let newStr = str + UTF8.CodeUnit.init(n)
        if str <= 122 && newStr > 122 {
            return newStr - 26
        }
        if str <= 90 && newStr > 90 {
            return newStr - 26
        }
        return newStr
    }
    return String(bytes: t, encoding: String.Encoding.utf8)!
}

```
