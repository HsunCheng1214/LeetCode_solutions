# 9. Palindrome Number
* (<span style="color: green"> Easy </span>)

Given an integer x, return true if x is a  palindrome, and false otherwise.
### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676861303/img/9-ex_zxrbou.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676861303/img/9-con_uyliom.png)


### code:
```
bool isPalindrome(int x){
    long reverse = 0, temp, r;

    if(x > 0 && x%10 != 0){
        temp = x;
        while(temp != 0){
            r = temp%10;
            reverse = reverse * 10 + r;
            temp /= 10;
        }

        if(x == reverse){
            return true;
        } else {
            return false;
        }
    } else if(x == 0){
        return true;
    } else {
        return false;
    }

    return 0;
}
```

### submissions:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676861303/img/9-sub_kvkciy.png)
