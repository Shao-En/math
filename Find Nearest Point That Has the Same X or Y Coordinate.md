# Find Nearest Point That Has the Same X or Y Coordinate
題目解析:
這題是一道二維平面上的點與點之間距離的問題。
給定一個二維平面上的點集合，在這個點集合中，找到與給定點最接近的點，並且這個點的X或Y坐標必須和給定點的X或Y坐標相同。

解題思路：

1. 定義一個變量ans和一個最小距離min_dis，初始化為-1和INT_MAX
1. 使用一個for循環遍歷點的集合
1. 判斷每個點的x坐標和y坐標是否與給定的x坐標和y坐標相等，如果相等，則計算這個點和給定點的距離
1. 如果這個距離小於目前的最小距離，則更新最小距離min_dis和ans的值
1. 最後，返回ans的值。

時間複雜度是O(n)
   
```
class Solution {
public:
    int nearestValidPoint(int x, int y, vector<vector<int>>& points) {
        int ans = -1;   //用來存放答案
        int dis;        //用來計算距離
        int min_dis = INT_MAX;  //存放最小距離
        //判斷點是否合法
        for(int i = 0; i < points.size(); i++){
            if(points[i][0] == x || points[i][1] == y){
                //合法
                dis = abs(points[i][0] - x) + abs(points[i][1] - y);   //計算距離
                if(dis < min_dis){
                    min_dis = dis;
                    ans = i;                                    //因為返回的是下標
                }
            }
        } 
        return ans;   //返回答案
    }
};
```


###### tags: `math`
 