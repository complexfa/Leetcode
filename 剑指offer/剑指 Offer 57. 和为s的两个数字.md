### [剑指 Offer 57. 和为s的两个数字](https://leetcode.cn/problems/he-wei-sde-liang-ge-shu-zi-lcof/)

#### 题目：

输入一个递增排序的数组和一个数字s，在数组中查找两个数，使得它们的和正好是s。如果有多对数字的和等于s，则输出任意一对即可。

```
示例1：
输入：nums = [2,7,11,15], target = 9
输出：[2,7] 或者 [7,2]

示例 2：
输入：nums = [10,26,30,31,47,60], target = 40
输出：[10,30] 或者 [30,10]
```

#### 思路：双指针

从左右两边进行遍历，当左右两指针指向的数加起来超过s，那么右指针向左移，如果小于s，那么左指针向右移，等于s，则返回这两个数。

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
      int left=0,right=nums.length - 1;
      while(left < right){
          if(nums[left] + nums[right] > target)
          right--;
          else if(nums[left] + nums[right] < target)
          left++;
          else return new int[] {nums[left],nums[right]};
          }
      return new int[] {};
      }
    
}
```

