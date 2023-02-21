# 4. Median of Two Sorted Arrays
* (<span style="color: red"> Hard </span>)

Given two sorted arrays nums1 and nums2 of size m and n respectively, 
return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).
### example:
![](https://i.imgur.com/0OzPOgK.png)

### constraints:
![](https://i.imgur.com/jiuEWWn.png)

### code:
```
double findMedianSortedArrays(int* nums1, int nums1Size, int* nums2, int nums2Size){
    int* temp;
    int i, j, x, y;
    int nums1Idx = 0, nums2Idx = 0, tempIdx = 0;
    float fx, fy, result;
    temp = malloc( (nums1Size+nums2Size) * sizeof(int));

    while(nums1Idx <= nums1Size - 1 && nums2Idx <= nums2Size - 1){
        if(nums1[nums1Idx] <= nums2[nums2Idx]){
            temp[tempIdx] = nums1[nums1Idx];
            nums1Idx ++;
        } else {
            temp[tempIdx] = nums2[nums2Idx];
            nums2Idx ++;
        }
        tempIdx ++;
    }

    if(nums1Idx > nums1Size - 1){
        while(nums2Idx <= nums2Size - 1){
            temp[tempIdx] = nums2[nums2Idx];
            nums2Idx ++;
            tempIdx ++;
        }
    } else {
        while (nums1Idx <= nums1Size - 1){
            temp[tempIdx] = nums1[nums1Idx];
            nums1Idx ++;
            tempIdx ++;
        }
    }

    for(i = 0 ; i < (nums1Size+nums2Size) ; i++){
        if(i == (nums1Size+nums2Size) - 1 && (i+1)%2 == 1){
            result = temp[(i+1)/2];
        } else if(i == (nums1Size+nums2Size) - 1 && (i+1)%2 == 0){
            x = i/2;
            y = x+1;
            fx = temp[x];
            fy = temp[y];
            result = (fx + fy)/2;
        }
    }
    return result;
}
```

### submissions:
![](https://i.imgur.com/mmeLpVC.png)
