# Sign of the Product of an Array
題目解析:
目算出給定數組中所有數的乘積的符號（正數或負數）。
解題思路:
利用負數的數量來判斷最後結果   
因為負負得正

1. 遍歷數組中的所有數，如果有0存在，則返回0，因為任何數乘0為0。
1. 累加負數的數量，如果負數的數量是偶數，則返回1（代表結果是正數），否則返回-1（代表結果是負數）
```
class Solution {
public:
    int arraySign(vector<int>& nums) {
        int ans = 0;   //ans 紀錄負數的個數

        //遍歷數組
        for(int i = 0; i < nums.size(); i++){
            if(nums[i] == 0){
                return 0;   //如果存在0，則整個數組的積是0
            }else if(nums[i] < 0){  
                ans++;     //計數負數的個數
            }
        }
        if(ans % 2 == 0){
            return 1;     //如果負數個數為偶數，則整個數組的積是正數
        }else{
            return -1;    //如果負數個數為奇數，則整個數組的積是負數
        }
    }
};
```
  

###### tags: `math`