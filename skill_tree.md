```swift
func solution(_ skill: String, _ skill_trees: [String]) -> Int {
    return skill_trees.filter {
        let filteredSkill = $0.filter {
            return skill.index(of: $0) != nil
        }
        return skill.hasPrefix(filteredSkill)
    }.count
}
```
