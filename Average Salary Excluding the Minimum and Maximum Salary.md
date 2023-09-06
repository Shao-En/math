# Average Salary Excluding the Minimum and Maximum Salary
給一組陣列計算排除掉最小值和最大值的平均數
法一:
先排序後去頭去尾
```C++=
class Solution {
public:
    double average(vector<int>& salary) {
        sort(salary.begin(), salary.end());     //排序salary陣列
        double sum;
        sum = accumulate(salary.begin() + 1, salary.end() -1, 0);
        return sum  / (salary.size() - 2);
    }
};
```   
法二:
再一次遍歷中利用INT_MAX, min, max找出最大值和最小值
```C++=
class Solution {
public:
    double average(vector<int>& salary) {
        double avg;
        int minV = INT_MAX;                //注意此處是假設為最大值
        int maxV = 0;
        for(int i = 0; i < salary.size(); i++){
            avg += salary[i];
            minV = min(salary[i], minV);
            maxV = max(salary[i], maxV);
        }
        avg -= (minV + maxV);
        avg /= (salary.size()-2);
        return avg;
    }
};
```
accumulate回傳值為int
![](https://i.imgur.com/VkD0k06.png)
 

###### tags: `math`


