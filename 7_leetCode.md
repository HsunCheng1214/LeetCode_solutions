# 7.Reverse Integer
* (<span style="color: orange"> Medium </span>)

Given a signed 32-bit integer x, return x with its digits reversed. 
If reversing x causes the value to go outside the signed 32-bit 
integer range [-231, 231 - 1], then return 0.

**Assume the environment does not allow you to store 64-bit integers (signed or unsigned).**

### example:
![](https://i.imgur.com/WWTQ9Mb.png)

### constraints:
![](https://i.imgur.com/a3IKFxq.png)

### code:
```
int reverse(int x){
    int r = 0;
    int max = INT_MAX/10, min = INT_MIN/10;
    
    while(x != 0){
        if(r > max || r < min){
            return 0;
        } 
        r = r*10 + x%10;
        x /= 10;
    }
    return r;
}
```

### submissions:
![](https://i.imgur.com/bgurgVm.png)
