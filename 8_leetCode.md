# 8.String to Integer(atoi)
* (<span style="color: orange"> Medium </span>)

Implement the myAtoi(string s) function, which converts a string to a 
32-bit signed integer (similar to C/C++'s atoi function).

The algorithm for myAtoi(string s) is as follows:

Read in and ignore any leading whitespace.
Check if the next character (if not already at the end of the string) 
is '-' or '+'. Read this character in if it is either. 
This determines if the final result is negative or positive respectively. 
Assume the result is positive if neither is present.
Read in next the characters until the next non-digit character or the end of the input is reached. 
The rest of the string is ignored.
Convert these digits into an integer (i.e. "123" -> 123, "0032" -> 32). 
If no digits were read, then the integer is 0. Change the sign as necessary (from step 2).
If the integer is out of the 32-bit signed integer range [-231, 231 - 1], 
then clamp the integer so that it remains in the range. Specifically, 
integers less than -231 should be clamped to -231, 
and integers greater than 231 - 1 should be clamped to 231 - 1.
Return the integer as the final result.

### Note:
![](https://i.imgur.com/oLOOQzK.png)

### example:
![](https://i.imgur.com/cWCmmqJ.png)
![](https://i.imgur.com/1lilbgk.png)
![](https://i.imgur.com/RoD8bm6.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676860519/img/8-con_tojewo.png)

### code:
```
int myAtoi(char * s){
    int total = 0;
    bool negative = false,yn = false;
    for(int i = 0;i<strlen(s);i++){
        if(s[i]==' '){
            if(yn == true)
                break;
        }
        else if(s[i]=='-'){
            if(yn == true){
                if(s[i-1]=='-'||s[i-1]=='+')
                    return 0;
                else
                    return total;
            }
            negative = true;
            yn = true;
        }
        else if(s[i]=='+'){
            if(yn == true){
                if(s[i-1]=='-'||s[i-1]=='+')
                    return 0;
                else
                    return total;
            }
            yn = true;
        }
        else if(s[i]>='0'&&s[i]<='9'){
            yn = true;
            if(total > 214748364 ||  total < -214748364){
                if(negative==true)
                    return INT_MIN;
                else
                    return INT_MAX;
            }
            else{
                total*=10;
                if(negative == true){
                    if(total<-2147483648+(s[i]-'0')){
                        return INT_MIN;
                    }
                    total-=(s[i]-'0');
                }
                else{
                    if(total>2147483647-(s[i]-'0')){
                        return INT_MAX;
                    }               
                    total += (s[i]-'0');
                }
            }
        }
        else{
            break;
        }
    }
    return total;
}
```

### submissions:
![](https://i.imgur.com/OvQA6uG.png)
