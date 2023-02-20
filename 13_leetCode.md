# 13.Roman to Integer
* (<span style="color: green"> Easy </span>)

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872390/img/13_bzuoku.png)

For example, 2 is written as II in Roman numeral, just two ones added together. 
12 is written as XII, which is simply X + II. The number 27 is written as XXVII, 
which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. 
However, the numeral for four is not IIII. Instead, the number four is written as IV. 
Because the one is before the five we subtract it making four. 
The same principle applies to the number nine, which is written as IX. 
There are six instances where subtraction is used:

* I can be placed before V (5) and X (10) to make 4 and 9. 
* X can be placed before L (50) and C (100) to make 40 and 90. 
* C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer.
### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872390/img/13-ex_mn9d81.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872390/img/13-con_sigtqr.png)

### code:
```
int romanToInt(char * s){
   int num = 0;
    for(int i = 0 ; i < strlen(s) ; i++){
        if( s[i] == 'M' ){
            num += 1000;
        } else if( s[i] == 'C' ){
            if(i+1 < strlen(s)){
                if( s[i+1] == 'M' ){
                    num += 900;
                    i++;
                } else if( s[i+1] == 'D' ){
                    num += 400;
                    i++;
                } else {
                    num+=100;
                }
            } else {
                num += 100;
            }
        } else if( s[i] == 'D' ){
            num+=500;
        } else if( s[i] == 'X' ){
            if(i+1 < strlen(s)){
                if( s[i+1] == 'C' ){
                    num += 90;
                    i++;
                } else if( s[i+1] == 'L' ){
                    num += 40;
                    i++;
                } else {
                    num+=10;
                }
            } else {
                num += 10;
            }
        } else if( s[i] == 'L' ){
            num+=50;
        } else if( s[i] == 'I' ){
            if(i+1 < strlen(s)){
                if( s[i+1] == 'X' ){
                    num += 9;
                    i++;
                } else if ( s[i+1] == 'V' ){
                    num += 4;
                    i++;
                } else {
                    num+=1;
                }
            } else {
                num+=1;
            }
        } else if( s[i] == 'V' ){
            num += 5;
        }
    }
    return num;
}
```

### submissions:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872390/img/13-sub_aut8r0.png)
