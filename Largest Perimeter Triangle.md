# Largest Perimeter Triangle
題目解析:
給定一個長度為n的整數數組A，求由A中的整數組成的三角形中周長最長的三角形周長。
如果不存在由A中的整數組成的三角形，則返回0。
注意：三角形的周長必須由三個長度為正整數的邊組成，且任意兩邊之和必須大於第三邊。


當三個線段中 較短兩邊的和大於最長邊 時，就可以組成三角形。
因為要求最大的，所以排序從最長邊開始找

解題思路:
這段程式碼的思路是：首先把陣列A從小到大排序，然後從最大的三個數字開始枚舉，如果這三個數字滿足條件，即前兩個數字之和大於第三個數字，則直接返回這三個數字的總和，否則繼續枚舉。如果所有的數字都不滿足條件，則返回0。
```   
class Solution {
public:
    int largestPerimeter(vector<int>& nums) {
        if(nums.size() < 3){
            return 0;
        }
        //先排序array 找到最大邊
        sort(nums.begin(), nums.end());
        //從最大邊開始測試三角形條件
        for(int i = nums.size() - 1; i >= 2; i--){
            if(nums[i] < (nums[i-1] + nums[i-2])){
                return (nums[i] + nums[i-1] + nums[i-2]);
            }
        }
        return 0;
    }
};
```
 

###### tags: `math`
