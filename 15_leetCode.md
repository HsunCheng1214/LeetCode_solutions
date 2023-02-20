# 15.3Sum
* (<span style="color: orange"> Medium </span>)

Given an integer array nums, return all the triplets **[nums[i], nums[j], nums[k]]** 
such that i != j, i != k, and j != k, and **nums[i] + nums[j] + nums[k]** == 0.

Notice that the solution set must not contain duplicate triplets.
### example:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676873799/img/15-ex_tmhycg.png)

### constraints:
![](https://res.cloudinary.com/dj6mprtik/image/upload/v1676873798/img/15-con_k1dwsa.png)

### code:
```
/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */

int comp(void* a, void* b) {
    return *(int*)a > *(int*)b ? 1 : -1;
}

int** threeSum(int* nums, int numsSize, int* returnSize, int** returnColumnSizes){
    int n = numsSize;
    qsort(nums, n, sizeof(int), comp);
    if(n < 3 || nums[0] > 0 || nums[0] + nums[1] + nums[2] > 0)
        return NULL;
    int** result = NULL;
    int i = 0, size = 0;
    int left = 0, right = 0;
    for(i = 0; i < n - 2 && nums[i] <= 0; i++) {
        left = i + 1;
        right = n - 1;
        while(left < right) {
            if(nums[i] + nums[left] + nums[right] > 0)
                right--;
            else if(nums[i] + nums[left] + nums[right] < 0)
                left++;
            else {
                size++;
                result = (int**)realloc(result, size * sizeof(int*));
                result[size - 1] = (int*)malloc(3 * sizeof(int));
                result[size - 1][0] = nums[i];
                result[size - 1][1] = nums[left];
                result[size - 1][2] = nums[right];
                while(left + 1 < n && nums[left] == nums[left + 1])
                    left++;
                while(right - 1 >= 0 && nums[right] == nums[right - 1])
                    right--;
                left++;
                right--;
            }
        }
        while(i + 1 < n && nums[i] == nums[i + 1])
            i++;
    }
    *returnSize = size;
    return result;
}
```

### submissions:
![]()
