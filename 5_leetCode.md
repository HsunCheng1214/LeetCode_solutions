# 5. Longest Palindromic Substring
* (<span style="color: orange"> Medium </span>)

Given a string s, return the longest palindromic substring in s.

### example:
![](https://i.imgur.com/S0bIvhx.png)

### constraints:
![](https://i.imgur.com/0y1CdFA.png)

### code:
```
char * longestPalindrome(char * s){
    int start_index = 0, max = 0, tempL = 0, tempR = 0;
    for(int i = 0 ; i<strlen(s) ; i++){
        tempL = i;
        tempR = i;
        
        while(tempR+1 < strlen(s)){
            if(s[tempR+1] == s[tempR]){
                tempR++;
            } else {
                break;
            }        
        }
        
        while(tempL-1 >= 0 && tempR+1 < strlen(s)){
            if(s[tempL-1] == s[tempR+1]){
                tempL--;
                tempR++;
            }
            else{
                break;
            }
        }
        
        if((tempR-tempL+1) > max){
            max = tempR - tempL+1;
            start_index = tempL;
        }
    }
    
    char *result = (char*)malloc( (max+1) * sizeof(char));
    strncpy(result, &s[start_index], max);
    result[max] = '\0';
    return result;
}

```

### submissions:
![](https://i.imgur.com/yR0tKTd.png)
