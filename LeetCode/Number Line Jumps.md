

```swift
func kangaroo(x1: Int, v1: Int, x2: Int, v2: Int) -> String {
    if v1 <= v2 { return "NO" }
    func find(_ dagdak1: Int,_ dagdak2: Int) -> String {
        if x1 + dagdak1 == x2 + dagdak2 { return "YES" }
        if x1 + dagdak1 > x2 + dagdak2 { return "NO" }
        return find(dagdak1 + v1, dagdak2 + v2)
    }
    return find(v1, v2)
}
```

- 요즘에 재귀가 익숙하지 않아서 일부러 써보려 한다
- 이런 단순한 재귀보다 Memorization과 Divide and Conquer를 의식해서 풀어봐야겠다