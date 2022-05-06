```golang
func twoSum(nums []int, target int) []int {
    m := make(map[int]int)
    for i, n := range nums {
        m[n] = i
    }
    for i, n := range nums {
        diff := target - n
        ps, ok := m[diff]
        if !ok || i == ps {
            continue
        }
        return []int{i, ps}
    }
    return nil
}
```
