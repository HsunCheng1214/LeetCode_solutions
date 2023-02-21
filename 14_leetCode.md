# 14.Longest Common Prefix
* (<span style="color: green"> Easy </span>)

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".
### example:
![](https://i.imgur.com/pSXUYui.png)

### constraints:
![](https://i.imgur.com/Pj4lbOa.png)

### code:
```
char * longestCommonPrefix(char ** strs, int strsSize){
    char * temp;
    int i,j;
    if(strsSize <= 0){
        return "";
    }

    temp = strs[0];
    for(i = 0 ; i < strsSize ; i++){
        j = 0;
        while(temp[j] && strs[i][j] && temp[j] == strs[i][j]){
            j++;
        }

        temp[j] = '\0';
    }

    return temp;
}
```

### submissions:
![](https://i.imgur.com/4w0bql4.png)
