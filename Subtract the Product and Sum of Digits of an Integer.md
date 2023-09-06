# Subtract the Product and Sum of Digits of an Integer

```
class Solution {
public:
    int subtractProductAndSum(int n) {
        int sum = 0, product = 1;
        while(n > 0 ){
            sum = sum + (n % 10);
            product = product * (n % 10);
            n = n / 10;
        }
        return product - sum;
    }
};
```
    
n = 5462


sum = 0 + 2
product = 1 * 2
n = 546

sum = 2 + 6
product = 2 * 6
n = 54

sum = 8 + 4
product = 12 * 4
n = 4

sum = 12 * 4
product = 48 * 4
n < 0 

###### tags: `math`
