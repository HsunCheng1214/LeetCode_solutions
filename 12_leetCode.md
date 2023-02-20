# 12.Integer to Roman
* (<span style="color: orange"> Medium </span>)

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676863950/img/12_nyjouw.png)
For example, 2 is written as II in Roman numeral, just two one's added together. 
12 is written as XII, which is simply X + II. 
The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. 
However, the numeral for four is not IIII. Instead, the number four is written as IV. 
Because the one is before the five we subtract it making four. 
The same principle applies to the number nine, which is written as IX. 
There are six instances where subtraction is used:

* I can be placed before V (5) and X (10) to make 4 and 9. 
* X can be placed before L (50) and C (100) to make 40 and 90. 
* C can be placed before D (500) and M (1000) to make 400 and 900.

Given an integer, convert it to a roman numeral.

### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676863950/img/12-ex_oopecg.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676863950/img/12-con_umcpis.png)

### code:
```
char * intToRoman(int num){
    char *result = (char*) malloc(sizeof(char) * 20);
    int i = 0;
    while(num > 0){
        if(num >= 1000){
            num -= 1000;
            result[i++] = 'M';
        }
        else if(num >= 900){
            num -= 900;
            result[i++] = 'C';
            result[i++] = 'M';
        }
        else if(num >= 500){
            num -= 500;
            result[i++] = 'D';
        }
        else if(num >= 400){
            num -= 400;
            result[i++] = 'C';
            result[i++] = 'D';
        }
        else if(num >= 100){
            num -= 100;
            result[i++] = 'C';
        }
        else if(num >= 90){
            num -= 90;
            result[i++] = 'X';
            result[i++] = 'C';
        }
        else if(num >= 50){
            num -= 50;
            result[i++] = 'L';
        }
        else if(num >= 40){
            num -= 40;
            result[i++] = 'X';
            result[i++] = 'L';
        }
        else if(num >= 10){
            num -= 10;
            result[i++] = 'X';
        }
        else if(num >= 9){
            num -= 9;
            result[i++] = 'I';
            result[i++] = 'X';
        }
        else if(num >= 5){
            num -= 5;
            result[i++] = 'V';
        }
        else if(num >= 4){
            num -=4 ;
            result[i++] = 'I';
            result[i++] = 'V';
        }
        else{
            num--;
            result[i++] = 'I';
        }
    }
    result[i] = '\0';
    return result;
}
```

### submissions:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676863950/img/12-sub_uyz0w4.png)
