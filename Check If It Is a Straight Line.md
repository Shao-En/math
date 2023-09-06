# Check If It Is a Straight Line

題目描述：  
給定幾個座標點，判斷這些點是否在一條直線上。

解題思路：
1. 計算出任意兩個點之間的斜率，並判斷是否一致。
1. 若所有的斜率都一致，則這些點在同一條直線上，否則不在。
1. 注意特殊情況，例如平行於y軸的直線，此時斜率無限大，需要特判。
```c++=
class Solution {
public:
    bool checkStraightLine(vector<vector<int>>& coordinates) {
        // 利用斜率計算，能形成一直線的斜率都相同
        // 注意 double 的資料型態在運算中不能變型，因為運算過程中用了 / 
        double a;
        double x = coordinates[1][0] - coordinates[0][0];   // 兩點之間的 x 差
        double y = coordinates[1][1] - coordinates[0][1];   // 兩點之間的 y 差
        if(x == 0){         // 避免除零問題
            a = INT_MAX;
        }else{
            a = y / x;      // 計算斜率
        }
        for(int i = 2; i < coordinates.size(); i++){   // 從第三個點開始比對
            double y1 = coordinates[i][1] - coordinates[i-1][1];   // 兩點之間的 y 差
            double x1 = coordinates[i][0] - coordinates[i-1][0];   // 兩點之間的 x 差
            double b;
            if(x1 == 0){  // 避免除零問題
                b = INT_MAX;
            }else{
                b = y1 / x1;    // 計算斜率
            }  
            if(a != b){    // 若斜率不同，則不能形成一直線
                return false;
            }
        }
        return true;   // 能形成一直線
    }
};
```


###### tags: `math`