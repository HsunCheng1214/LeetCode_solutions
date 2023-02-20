# 14.Longest Common Prefix
* (<span style="color: green"> Easy </span>)

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".
### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872818/img/14-ex_gi0qbm.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872818/img/14-con_k5ewbb.png)

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
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676872818/img/14-sub_w3jx4j.png)
