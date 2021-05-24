### Group Anagrams

생각의 전환이 필요한 문제





```swift
class Solution {
    func groupAnagrams(_ strs: [String]) -> [[String]] {
        var result = Dictionary<String, [String]>()
        
        for str in strs {
            result[String(str.sorted()), default: [String]()].append(str)
        }
        
        return result.values.map { (arr) -> [String] in
            return arr
        }
    }
}
```

