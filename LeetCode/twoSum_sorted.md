```golang
func twoSum(nums []int, target int) []int {
    sorted := make([]int, len(nums))
    for i, n := range nums {
        sorted[i] = n
    }
    sort.Ints(sorted)
    var res []int
    OUT: for i, n := range nums {
        pos := sort.SearchInts(sorted, target - n)
        if pos == len(sorted) || (n + sorted[pos]) != target {
            continue
        }
        for j:=i+1;j<len(nums);j++ {
            if nums[j] == sorted[pos] {
                res = []int{i, j}
                break OUT
            }
        }
    }
    return res
}
```
