### Binary Tree Level Order Traversal



#### Recursive(DFS)

```swift
class Solution {
    func levelOrder(_ root: TreeNode?) -> [[Int]] {
        var dict = [Int: [Int]]()
        func recursive(_ node: TreeNode?, count: Int) {
            if node == nil { return }
            dict[count, default: [Int]()].append(node!.val)
            recursive(node?.left, count: count+1)
            recursive(node?.right, count: count+1)
        }
        recursive(root, count: 1)
        return dict.sorted(by: { $0.key < $1.key }).map { (element) -> [Int] in
            return element.value
        }
    }
}
```



#### BFS

```swift
class Solution {
    func levelOrder(_ root: TreeNode?) -> [[Int]] {
        var result = [[Int]]()
        var queue = [root]
        
        while !queue.isEmpty {
            var level = [Int]()
            for _ in 0..<queue.count {
                let e = queue.removeFirst()
                if let e = e {
                    level.append(e.val)
                    queue.append(e.left)
                    queue.append(e.right)
                }
            }
            if !level.isEmpty { result.append(level) }
        }
        return result
    }
}
```

