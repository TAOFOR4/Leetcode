```
int removeDuplicates(int* nums, int numsSize) {
    if (numsSize == 0) {
        return 0;  // Edge case: empty array, no unique elements.
    }

    int j = 0; // Initialize a variable to keep track of the current unique element index.

    for (int i = 1; i < numsSize; i++) {
        if (nums[i] != nums[j]) {
            // If the current element is different from the previous unique element,
            // increment j and update nums[j] with the current element.
            j++;
            nums[j] = nums[i];
        }
    }

    // j + 1 represents the number of unique elements.
    return j + 1;
}
```