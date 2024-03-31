```
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* productExceptSelf(int* nums, int numsSize, int* returnSize) {
    *returnSize = numsSize;
    int* result = (int*)malloc(*returnSize*sizeof(int));
    int nums_of_zero = 0;
    for(int i=0;i<numsSize;i++)
    {
        if(nums[i]==0)
        {
            nums_of_zero++;
        }
    }

    if(nums_of_zero>1)
    {
        for(int i=0;i<numsSize;i++)
        {
            result[i]=0;
        }

        return result;
    }

    int product = 1;
    for(int i=0;i<numsSize;i++)
    {
        if(nums[i])
        {
            product*=nums[i];
        }
    }

    if(nums_of_zero==1)
    {
        for(int i=0;i<numsSize;i++)
        {
            if(nums[i])
            {
                result[i]=0;
            }
            else
            {
                result[i]=product;
            }
        }

        return result;
    }

    for(int i=0;i<numsSize;i++)
    {
        result[i]=product/nums[i];
    }

    return result;

}
```