# 3. Longest Substring Without Repeating Characters
* (<span style="color: orange"> Medium </span>)

Given a string s, find the length of the longest substring
without repeating characters.

### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676857427/img/3-ex_pcaru1.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676857505/img/3-con_p5tk0t.png)

### code:
```
int lengthOfLongestSubstring(char * s){
    int *arr = (int*)malloc(128 * sizeof(int));
    int i, max = 0, temp = 0;

    for(i = 0 ; i < strlen(s) ; i++){
        if((arr[s[i]]) >= temp){
            temp = arr[s[i]] + 1;
            arr[s[i]] = i;
        } else {
            arr[s[i]] = i;
            if(i-temp + 1 > max){
                max = i - temp + 1;
            }
        }
    }
    return max;
}
```

### submissions:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676857427/img/3-sub_kfr9yq.png)
