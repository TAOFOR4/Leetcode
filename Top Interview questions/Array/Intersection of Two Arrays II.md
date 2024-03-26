´´´
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* intersect(int* nums1, int nums1Size, int* nums2, int nums2Size, int* returnSize) {
    if(nums1Size>nums2Size)
    {
        *returnSize = nums2Size;
    }
    else
    {
        *returnSize = nums1Size;
    }

    int* nums3 = (int*)malloc(*returnSize * sizeof(int));

    int k = 0;

    int hash[1001]={0};

    for(int i=0; i<nums1Size;i++)
    {
        hash[nums1[i]]++;
    }
    for(int i=0; i<nums2Size;i++)
    {
        if(hash[nums2[i]]>0)
        {
            nums3[k]=nums2[i];
            hash[nums2[i]]--;
            k++;

        }
    }

    *returnSize = k;

    return nums3;

}
´´´