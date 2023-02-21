# 6.Zigzag Conversion
* (<span style="color: orange"> Medium </span>)

The string "PAYPALISHIRING" is written in a zigzag pattern on a 
given number of rows like this: 
(you may want to display this pattern in a fixed font for better legibility)

![](https://i.imgur.com/Mj909OP.png)

And then read line by line: "PAHNAPLSIIGYIR"
Write the code that will take a string and make this conversion given a number of rows:

![](https://i.imgur.com/Usado0A.png)

### example:
![](https://i.imgur.com/yn9PD8e.png)

### constraints:
![](https://i.imgur.com/Z4xVBkx.png)


### code:
```
char * convert(char * s, int numRows){
    int step = (numRows-1)*2, resultIndex = 0, jump = 0, s_size = strlen(s);
    char *result = (char *)malloc((s_size+1) * sizeof(char));
    result[s_size] = '\0';

    if(strlen(s) == 1 || numRows == 1)
        return s;

    for(int i = 0 ; i < numRows ; i++){
        int jump = 0;
        while(jump < s_size){
            if(jump+i < s_size && i != (numRows-1)){
                result[resultIndex] = s[jump+i];
                resultIndex++;
            }
            jump += step;
            if(jump-i < s_size && i != 0){
                result[resultIndex] = s[jump-i];
                resultIndex++;
            }
        }
    }
    
    return result;
}
```

### submissions:
![](https://i.imgur.com/C07dpLM.png)
