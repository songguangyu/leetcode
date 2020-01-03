## leedcode地址
https://leetcode.com/problems/remove-duplicates-from-sorted-array/description

## 解题方案
因为有序 所以O(1)

```
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    const size = nums.length;
    let index = 0;
    for (let i = 0; i < size; i++) {
        if (nums[i] !== nums[index]) {
            index++;
            nums[index] = nums[i]
        }
    }
    return index + 1;
};
```