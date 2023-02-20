# 16.3Sum Closest
* (<span style="color: orange"> Medium </span>)

Given an integer array nums of length n and an integer target, 
find three integers in nums such that the sum is closest to target.

Return the sum of the three integers.

You may assume that each input would have exactly one solution.
### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676874051/img/16-ex_iyvqba.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676874050/img/16-con_ar6dto.png)


### code:
```
int cmp(const void *a, const void *b){
    return *(int *)a - *(int *)b;
}

int threeSumClosest(int* nums, int numsSize, int target){
    int left = 0, right = 99999, closest = 99999, tempsum=0;
    qsort(nums, numsSize, sizeof(int), cmp); 
    for(int i = 0 ; i < numsSize - 2 ; i++){
        left = i + 1;
        right = numsSize - 1;
        while(right > left){
            tempsum = nums[i] + nums[left] + nums[right];
            if(abs(target - tempsum) < abs(target - closest)){
                closest = tempsum;
            }
            if(tempsum<target){
                left++;
            }   
            else if(tempsum>target){
                right--;
            }
            else{
                break;
            }
        }
    }
    return closest;
}
```

### submissions:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676874050/img/16-sub_nh81yo.png)
