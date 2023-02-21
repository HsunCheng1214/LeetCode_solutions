# 11. Container With Most Water
* (<span style="color: orange"> Medium </span>)

You are given an integer array height of length n. 
There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.
### example:
![](https://i.imgur.com/xwTwKNV.png)

### constraints:
![](https://i.imgur.com/iVYA7jJ.png)

### code:
```
int maxArea(int* height, int heightSize){
    int left = 0, right = heightSize - 1;
    int tempArea, maxArea = 0;

    while(left < right){
        if(height[left] < height[right]){
            tempArea = (right - left) * height[left];
            if(tempArea > maxArea){
                maxArea = tempArea;
            }
            left ++;
        } else {
            tempArea = (right - left) * height[right];
            if(tempArea > maxArea){
                maxArea = tempArea;
            }
            right --;
        }
    }
    return maxArea;
} 
```

### submissions:
![](https://i.imgur.com/zfjZQTU.png)
