# C++ 解法
# 1. 两数之和
给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target  的那 两个 整数，并返回它们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

你可以按任意顺序返回答案。

 

示例 1：

输入：nums = [2,7,11,15], target = 9
输出：[0,1]
解释：因为 nums[0] + nums[1] == 9 ，返回 [0, 1] 。
示例 2：

输入：nums = [3,2,4], target = 6
输出：[1,2]
示例 3：

输入：nums = [3,3], target = 6
输出：[0,1]
 

提示：

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
只会存在一个有效答案
```Cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int count = nums.size();
        vector<int> ans;
        for(int i=0;i<count;i++){
            for(int j=count-1;j>i;j--){
                if(nums[i] + nums[j] == target){
                    ans.push_back(i);
                    ans.push_back(j);
                    return ans;
                }
            }
        }
        return ans;
    }
};
```
- - -
# 11. 盛最多水的容器
https://leetcode.cn/problems/container-with-most-water/description/  
给定一个长度为 n 的整数数组 height 。有 n 条垂线，第 i 条线的两个端点是 (i, 0) 和 (i, height[i]) 。

找出其中的两条线，使得它们与 x 轴共同构成的容器可以容纳最多的水。

返回容器可以储存的最大水量。

说明：你不能倾斜容器。

 

示例 1：



输入：[1,8,6,2,5,4,8,3,7]
输出：49 
解释：图中垂直线代表输入数组 [1,8,6,2,5,4,8,3,7]。在此情况下，容器能够容纳水（表示为蓝色部分）的最大值为 49。  
示例 2：

输入：height = [1,1]
输出：1
 

提示：

n == height.length  
2 <= n <= 105  
0 <= height[i] <= 104  

## 双指针方法
```C++

```


# 13. 罗马数字转整数

https://leetcode.cn/problems/roman-to-integer/  
罗马数字包含以下七种字符: I， V， X， L，C，D 和 M。

    字符          数值
    I             1
    V             5
    X             10
    L             50
    C             100
    D             500
    M             1000
例如， 罗马数字 2 写做 II ，即为两个并列的 1 。12 写做 XII ，即为 X + II 。 27 写做  XXVII, 即为 XX + V + II 。

通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况：

    I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。
    X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 
    C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。
给定一个罗马数字，将其转换成整数。

 

示例 1:

    输入: s = "III"
    输出: 3
示例 2:

    输入: s = "IV"
    输出: 4
示例 3:

    输入: s = "IX"
    输出: 9
示例 4:

    输入: s = "LVIII"
    输出: 58
    解释: L = 50, V= 5, III = 3.
示例 5:

    输入: s = "MCMXCIV"
    输出: 1994
    解释: M = 1000, CM = 900, XC = 90, IV = 4.
 

提示：

1 <= s.length <= 15
s 仅含字符 ('I', 'V', 'X', 'L', 'C', 'D', 'M')
题目数据保证 s 是一个有效的罗马数字，且表示整数在范围 [1, 3999] 内
题目所给测试用例皆符合罗马数字书写规则，不会出现跨位等情况。
IL 和 IM 这样的例子并不符合题目要求，49 应该写作 XLIX，999 应该写作 CMXCIX 。
关于罗马数字的详尽书写规则，可以参考 罗马数字 - Mathematics 。

## 这解法属实有点伞兵
## 方法一 暴力解（类似C语言）
```C++

class Solution {
public:
    int romanToInt(string s) {
        int count = s.size();
        int sum=0;
        for(int i = 0; i < count; i++){
            if(s[i] == 'I'){
                if(s[i+1] == 'X'){
                    sum=sum-2;
                }
                else if(s[i+1] == 'V'){
                    sum=sum-2;
                }
                sum=sum+1;
            }
            else if(s[i]=='V'){
                sum=sum+5;
            }
            else if(s[i]=='X'){
                if(s[i+1]=='L'){
                    sum=sum-20;
                }
                else if(s[i+1]=='C'){
                    sum=sum-20;
                }
                sum=sum+10;
            }
            else if(s[i]=='L'){
                sum=sum+50;
            }
            else if(s[i]=='C'){
                if(s[i+1]=='D'){
                    sum=sum-200;
                }
                else if(s[i+1]=='M'){
                    sum=sum-200;
                }
                sum=sum+100;
            }
            else if(s[i]=='D'){
                sum=sum+500;
            }
            if(s[i]=='M'){
                sum=sum+1000;
            }
        }
        return sum;
    }
};

```
## 优化解法
利用 

```C++
class Solution {
public:
    int romanToInt(string s) {
        int ans = 0;
        int n = s.size();
        for (int i = 0; i < n; i++) {
            int sum = map[s[i]];
            if (i < n - 1 && value < map[s[i + 1]]) {
                ans -= sum;
            } else {
                ans += sum;
            }
        }
        return ans;
    }
    unordered_map<char, int> map = {
        {'I', 1},
        {'V', 5},
        {'X', 10},
        {'L', 50},
        {'C', 100},
        {'D', 500},
        {'M', 1000},
    };
};


```

- - -


# 14
