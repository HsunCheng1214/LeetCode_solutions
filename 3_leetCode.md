# 3. Longest Substring Without Repeating Characters
* (<span style="color: orange"> Medium </span>)

Given a string s, find the length of the longest substring
without repeating characters.

### example:
![](https://i.imgur.com/WiYdk56.png)

### constraints:
![](https://i.imgur.com/ZSQ44Ac.png)

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
![](https://i.imgur.com/fQgErHN.png)
