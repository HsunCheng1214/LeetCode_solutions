# 1.Two Sum
* (<span style="color:green"> Easy </span>)

Given an array of integers nums and an integer target, 
return indices of the two numbers such that they add up to target.

You may assume that each input would have 
exactly one solution, and you may not use the 
same element twice.

You can return the answer in any order.

### example:
![](https://i.imgur.com/idkTAtl.png)

### constraints:
![](https://i.imgur.com/0v4YU7v.png)

### Follow-up:
Can you come up with an algorithm 
that is less than O(n2) time complexity ?

### code:
```
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* nums, int numsSize, int target, int* returnSize){
    int yn = -1;
    *returnSize = 2;
    int *arr = malloc(*returnSize * sizeof(int));
    for(int i = 0 ; i < numsSize ; i++){
        for(int j = 0; j < numsSize ; j++){
            if(i!=j)
                if(nums[i] + nums[j] == target){
                    arr[0] = i;
                    arr[1] = j;
                    yn = 1;
                    break;
                }
        }
        if(yn == 1)
            break;
    } if(yn == -1) {
        *returnSize = 0;
        free(arr);
    }
    return arr;
}

```

### submissions:
![](https://i.imgur.com/89OMajw.png)
