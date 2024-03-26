```
void reverse(int* nums, int start, int end) {
    int temp;
    while (start < end) {
        temp = nums[start];
        nums[start] = nums[end];
        nums[end] = temp;
        start++;
        end--;
    }
}

void rotate(int* nums, int numsSize, int k) {
    k = k % numsSize; // * Handle cases where k > numsSize
    
    reverse(nums, 0, numsSize - 1); // Step 1: Reverse the entire array
    reverse(nums, 0, k - 1); // Step 2: Reverse the first k elements
    reverse(nums, k, numsSize - 1); // Step 3: Reverse the rest
}
```