```
void moveZeroes(int* nums, int numsSize) {
    int modify=0;

    for(int i=0;i<numsSize;i++)
    {
        if(nums[i])
        {
            if(modify==i)
            {
                modify++;
            }
            else
            {
                nums[modify++]=nums[i];
                nums[i]=0;
            }
        }
    }
}
```