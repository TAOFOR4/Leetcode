```
/*
 * 1679. Max Number of K-Sum Pairs
 *
 * You are given an integer array nums and an integer k.
 * 
 * In one operation, you can pick two numbers from the 
 * array whose sum equals k and remove them from the array.
 * 
 * Return the maximum number of operations you can perform 
 * on the array.
 *
 * 1 <= nums.length <= 10^5
 * 1 <= nums[i] <= 10^9
 * 1 <= k <= 10^9
 */

int cmp(const void *a, const void *b)
{
    return *((int *)a) - *((int *)b);
}

int maxOperations(int* nums, int numsSize, int k){

    /*
     * Input:
     *  nums,
     *  numsSize,
     *  k
     */

    int ans = 0;

    /* Sort nums by value in ascending order */
    qsort(nums, numsSize, sizeof(int), cmp);

    /* 
     * Two pointers point to leftmost and rightmost 
     * compare the sum of values and move the pointer accordingly
     */
    for (int i = 0, j = numsSize - 1; i < j; ) {

        if (nums[i] + nums[j] > k) {
            j--;
        }
        else if (nums[i] + nums[j] < k) {
            i++;
        }
        else {
            ans++;
            i++;
            j--;
        }
    }
    
    /*
     * Return the maximum number of operations you can perform 
     * on the array.
     */

    return ans;
}


```