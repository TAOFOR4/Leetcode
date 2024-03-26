```
int singleNumber(int* nums, int numsSize) {
    int hash[60000]={0};
    for(int i=0; i<numsSize;i++)
    {
        hash[nums[i]+30000]++;
    }
    for(int i=0; i<numsSize;i++)
    {
        if(hash[nums[i]+30000]==1)
        {
            return nums[i];
        }
    }

    return 0;
}

```