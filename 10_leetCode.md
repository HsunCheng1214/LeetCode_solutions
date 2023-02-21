# 10.Regular Expression Matching
* (<span style="color:red"> Hard </span>)

Given an input string s and a pattern p, 
implement regular expression matching with support for '.' and '*' where:

* '.' Matches any single character.????
* '*' Matches zero or more of the preceding element.

The matching should cover the entire input string (not partial).

### example:
![](https://i.imgur.com/vOLfPMr.png)

### constraints:
![](https://i.imgur.com/lAtjBxC.png)


### code:
```
bool isMatch(char * s, char * p){
    if(strlen(s) == 0 && strlen(p) == 0){
        return true;
    }

    if(strlen(p) > 1 && p[1] == '*'){
        if(isMatch(s, &p[2])){
            return true;
        }

        if((p[0] == '.' || s[0] == p[0]) && strlen(s) > 0){
            return isMatch(&s[1], p);
        }
    } else {
        if((p[0] == '.' || p[0] == s[0]) && strlen(s) > 0){
            return isMatch(&s[1], &p[1]);
        }
        return false;
    }
    return false;
}
```

### submissions:
![](https://i.imgur.com/lAtjBxC.png)


